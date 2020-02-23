<template>
  <div>
    <h2>Right Tab</h2>

    <p class="counter-text">
      Counter :
      <span class="counter-amount">{{counter}}</span>
    </p>

    <button v-on:click="increaseCounter()">Increase counter</button>
    <button v-on:click="resetCounter()">Reset counter</button>
  </div>
</template>

<script>
import { EventBus } from "../service/EventBus.js";

export default {
  name: "RightTab",

  data: function() {
    return {
      counter: 0
    };
  },

  methods: {
    increaseCounter() {
      this.counter++;
      this.emitCounter();
    },

    resetCounter() {
      this.counter = 0;
      this.emitCounter();
    },

    emitCounter() {
      EventBus.$emit("COUNTER", this.counter);
      console.log(`emiting COUNTER ${this.counter}`);
    }
  },
  created: function() {
    EventBus.$on("DOUBLE_COUNTER", () => {
      this.counter *= 2;
      this.emitCounter();
    });
    this.emitCounter();
  }
};
</script>

<style scoped>
.counter-text {
  font-weight: bold;
}
.counter-amount {
  padding: 3px 5px;
  border: 2px solid lightblue;
  border-radius: 3px;
  background-color: lightgrey;
}
</style>
