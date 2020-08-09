<template>
  <div id="app">
    <StyledHeader
      title="Title Name Goes Here"
      description="This is the description or problem statement of the application"
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
