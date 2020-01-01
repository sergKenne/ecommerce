<template>
  <div id="app">
    <div id="loading" v-if="loading">
      <img src="/static/img/loader.gif" alt="loading">
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      loading: false
    }
  },
  created() {
    this.$eventBus.$on("loadingStatus", payload => {
      this.loading = payload;
    });
  } 
}
</script>

<style>

</style>
