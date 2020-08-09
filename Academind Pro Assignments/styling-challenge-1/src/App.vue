<template>
  <div id="app">
    <StyledHeader
      title="Styling Assignment 1"
      description="1: Alternate between highlight and shrink using a setINterval function, attacth a CSS Class to a div. "
    />
  </div>
</template>

<script>
import StyledHeader  from './components/StyledHeader.vue';
export default {
  name: "App",
  components: {
    StyledHeader
  }
};
</script>

<style>
body {
  padding: 0px;
  margin: 0px;
  border: 0px;
}
</style>
