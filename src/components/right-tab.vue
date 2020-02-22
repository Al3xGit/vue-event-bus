<template>
  <div>
    <h2>Right Tab</h2>
    <p>Counter is at {{counter}}.</p>
    <button type="button" name="button" v-on:click="counter++">Increase counter</button>
  </div>
</template>

<script>
export default {
  name: 'RightTab',
  data: function() {
    return {
      counter: 1,
    };
  },
}
</script>

<style scoped>

</style>
