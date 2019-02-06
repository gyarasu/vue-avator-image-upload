<template>
  <div
    class="avator">
    <img
      class="avator__icon"
      :src="avatorUrl" />
    <input
      class="avator__input"
      type="file"
      id="avator-input"
      accept="image/png,image/jpeg,image/gif"
      v-on:change="uploadAvator" />
    <button
      class="avator__button"
      v-on:click="selectAvator">
      <img
        src="../assets/camera.svg" />
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    selectAvator() {
      const input = document.querySelector('#avator-input');
      input.click();
    },
    uploadAvator(e) {
      e.preventDefault();

      // nothing to do when 'files' is empty
      if (e.target.files.length === 0) {
        return null;
      }

      const avatorfile = e.target.files[0];

      // TODO: add upload process with same file name
      // eslint-disable-next-line
      console.log(avatorfile);


      // add timestamp to image url to reload
      this.avatorUrl = `${this.avatorUrl}?timestamp=${Date.now()}`
    },
  },
  data() {
    return {
      // TODO: Replace Your avator Path
      avatorUrl: '/profile.svg',
    };
  },
};
</script>

<style>
.avator {
  position: relative;
  display: inline-block;
}
.avator__icon {
  height: 64px;
  width: 64px;
  border-radius: 50%;
}

.avator__input {
  display: none;
}

.avator__button {
  /* reset button style */
  background-color: transparent;
  border: none;
  cursor: pointer;
  outline: none;
  padding: 0;
  appearance: none;

  /* position setting*/
  position: absolute;
  right: -4px;
  bottom: 4px;

  border-radius: 50%;
  box-shadow: 1px 1px rgba(0, 0, 0, 0.1);
  background-color: white;
  padding: 2px;
}


</style>