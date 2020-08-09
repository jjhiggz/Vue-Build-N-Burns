<template>
  <div id="app">
    <StyledHeader
      title="Styling Assignment 1"
      description="1: Alternate between highlight and shrink using a setINterval function, attacth a CSS Class to a div. "
    />
    <button 
      @click="startEffect"
    >
      START EFFECT
    </button>
    <div
      id="effect"
      :class="{highlight: highlight}"  
    >

    </div>
  </div>
</template>

<script>
import StyledHeader from "./components/StyledHeader.vue";
export default {
  name: "App",
  data() {
    return {
      highlight: false,
    }
  },
  components: {
    StyledHeader
  },
  methods: {
    startEffect(){
      let vm = this;
      let interval = setInterval( () => {
        vm.highlight = !vm.highlight
      } ,100)
      setTimeout(() => {
        clearInterval(interval)
      },3000)
    },

  }
};
</script>

<style>
body {
  padding: 0px;
  margin: 0px;
  border: 0px;
}
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
#effect {
  width: 100px;
  height: 100px;
  border: 1px solid black
}
.highlight {
  background-color: yellow;
}
</style>
