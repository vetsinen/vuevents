<template>
  <div id="app">
    <Events msg="Wielcomen to Your Vue.js App"/>
  </div>
</template>

<script>
import Events from './components/Events.vue'


export default {
  name: 'app',
  components: {
    Events
  }
}
</script>

<style>
#app {

}
</style>
