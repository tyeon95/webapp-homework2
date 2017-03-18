<template>
  <div id="app">
    <div v-if="$store.getters.loggedIn">
      <iccs340-top-barnav></iccs340-top-barnav>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
    Iccs340TopBarnav: require('./TopBarnav')
  }
}
</script>

<style>
</style>
