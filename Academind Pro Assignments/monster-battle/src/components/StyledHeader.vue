<template>
  <div id="header-background">
    <div id="header-content">
      <div id="title-and-description">
        <h1
          :style="{
            alignSelf:'flex-start',
            marginTop: 0 + 'px',
            marginBottom: 0 + 'px',
            fontSize: 20 + 'px',
          }"
        >
        {{title}}
        </h1>
        <p
          :style = "{
            fontSize: 10 + 'px',
            marginTop: 0 + 'px',
            marginBottom: 0 + 'px',
          }"
        >
          {{description}}
        </p>
      </div>
      <img
        src="../assets/mimoji.jpg"
        :style="{ 
        fontFamily:'Rubik Mono One',
        width: 70 + 'px',
        height: 70 + 'px',
        alignSelf: 'center',
        borderRadius: 50 + '% '
      }"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "StyledHeader",
  props: {
    title: {String},
    description: {String},
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Rubik+Mono+One&display=swap");
#header-content {
  font-family: "Rubik Mono One";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: space-between;
  margin-left: 40px;
  margin-right: 40px;
  color: white;
  
}
#header-background {
  background-color: black;
  width: 100%;
  margin: 0px;
  padding: 0px;
  
}
</style>