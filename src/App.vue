<template>
  <div id="app">
    <h1>Test</h1>
    <left-tab></left-tab>
  </div>
</template>

<script>
import LeftTab from './components/left-tab.vue'

export default {
  name: 'App',
  components: {
    'left-tab': LeftTab,
  }
}
</script>

<style>
#app {

}
</style>
