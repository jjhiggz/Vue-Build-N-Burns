<template>
  <div id="app">
    <StyledHeader
      title="Conditionals And Lists"
      description="1) hook up button to toggle display of two paragraphs 2) Create a list of objects, and iterate through each object  "
    />
    <div 
      class="container"
    >
      <p
        v-if="isGoodPerson"
        class="paragraph"
      >
        Bro, you are a great person I'm really happy that you decided to do the right thing. If you ever are feeling down, feel free to give me a call at 777-555-6909
      </p>
      <p
        v-else
        class="paragraph"
      >
        Dude You are the absolute Worst. I hope you eat a bag of worms thinking that they were gummy worms.
      </p>
      <button
        :style="{backgroundColor:'red'+'!important'}"
        @click="isGoodPerson = false"
      >
        be bad person
      </button>
      <button
        :style="{backgroundColor:'green'+'!important'}"
        @click="isGoodPerson = true"
      >
        be good person
      </button>
      <h1>To Do List</h1>
      <span class="tasks-container" :key="toDoTask.task" v-for="(toDoTask, index) in toDoList">
        <h2>Task #: {{index}}</h2>
        <ul>
          <li :key="value" v-for="(value,key) in toDoTask">
            {{key}}: {{value}}
          </li>
        </ul>
      </span>
    </div>
  </div>
</template>

<script>
import StyledHeader  from './components/StyledHeader.vue';
let goodToDoList = [
  {
    task: 'Go help an old lady cross the street',
    time: 'morning',
  },
  {
    task: 'Do the dishes for your mom',
    time: 'evening',
  },
  {
    task: 'Eat Healthy',
    time: 'all day',
  },
  {
    task: 'Call your grandparents and tell them hello',
    time: 'noon',
  },
]
let evilToDoList = [
  {
    task: 'Punch a homeless man in the face',
    time: 'morning',
  },
  {
    task: 'eat half of the last apple and put it back in the fridge',
    time: 'evening',
  },
  {
    task: 'Kick the dog',
    time: 'all day',
  },
  {
    task: 'Sell drugs to children',
    time: 'noon',
  },
]
export default {
  name: "App",
  components: {
    StyledHeader
  },
  data() {
    return {
      isGoodPerson: true,
    }
  },
  computed: {
    toDoList(){
      return this.isGoodPerson ? goodToDoList : evilToDoList
    }
  },
};
</script>

<style>
body {
  padding: 0px;
  margin: 0px;
  border: 0px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.app{
  display: flex !important;
  align-items: center;
  /* justify-content: center; */
}
.container{
  display: flex;
  flex-direction: column;
  align-items: center;
  border: solid black;
}
.paragraph{
  width: 200px;
}
.tasks-container {
  text-align: center;
}
</style>
