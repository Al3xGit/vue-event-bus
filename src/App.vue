<template>
  <div id="app">
    <h1 class='app-title'>Event bus POC</h1>

    <div class="tabs-container">
      <left-tab class="tab"></left-tab>
      <right-tab class="tab"></right-tab>
    </div>
  </div>
</template>

<script>
import LeftTab from './components/left-tab.vue'
import RightTab from './components/right-tab.vue'

export default {
  name: 'App',
  components: {
    'left-tab': LeftTab,
    'right-tab': RightTab,
  }
}
</script>

<style scoped>
.app-title {
  text-align: center;
}

.tabs-container {
  display: flex;
  flex-direction: row;
}

.tab {
  width: 50%;
  min-width: 200px;
  min-height: 300px;
  border: 1px solid grey;
  padding: 20px;
  margin: 20px;
}
</style>
