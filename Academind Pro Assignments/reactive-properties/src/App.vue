<template>
  <div id="app">
    <p>The Current counter is:{{ counter }}</p>
    <button @click="counter += 5">Add 5</button>
    <button @click="counter += 1">Add 1</button>
    <p>The result is :{{ result }}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      counter: 0,
    }
  },
  computed: {
    result() {
      return Math.sqrt(this.counter);
    },
  },
  watch: {
    counter: function() {
      var vm = this;
      setTimeout(function(){
        vm.counter = 0;
        console.log('time')
      }, 5000 )
    }
  },
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
