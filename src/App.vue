<template>
  <h2>Number {{ state.count }}</h2>
  <h2>Double Number {{ state.double }}</h2>
  <button @click = "updateNumber(true)" >Increase number</button>
  <button @click = "updateNumber(false)" >Decrease number</button>
</template>

<script>
import { reactive, computed } from 'vue'

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed (() => state.count * 2)
    })

    function updateNumber(increase) {
      if (increase) {
        state.count++
      } else {
        state.count--
      }
    }

    return {
      state,
      updateNumber
    }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #000;
  height: 100vh;
  text-align: center;
  color: #fff;
}

button {
  margin: 10px 5px;
  padding: 12px 17px;
  border-radius: 15px;
  border: none;
  color: #000;
  background: #eee;
}



</style>
