<template>
  <div id="app">
    <profile></profile>
  </div>
</template>

<script>
import Profile from '@/components/Profile';

export default {
  name: 'app',
  components: {
    profile: Profile,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
