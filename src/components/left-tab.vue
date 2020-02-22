<template>
  <div>
    <h2>Left Tab</h2>
    <p>{{paragraphMessage}}</p>
    <button v-on:click="emitDoubleEvent()">Double counter in right tab</button>
  </div>
</template>

<script>
import { EventBus } from '../service/EventBus.js';

export default {
  name: 'LeftTab',
  data: function() {
    return {
      displayClick: 0,
      paragraphMessage: '...',
    }
  },
  methods: {
    emitDoubleEvent() {
      EventBus.$emit('DOUBLE_COUNTER');
    },
  },
  created: function() {
    EventBus.$on('COUNTER', nbClick => {
      this.paragraphMessage = `The counter in right panel is at ${nbClick}` ;
    });
  }
}
</script>

<style scoped>
  h2 {
    color: grey;
  }

</style>
