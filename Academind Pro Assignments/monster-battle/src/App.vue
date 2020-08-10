<template>
  <div id="app">
    <StyledHeader
      title="Monster App"
      description="It's like Pokemon but way shittier"
    />
    <div class="characters-container">
      <Character
        :character="player"
      />
      <Character
        :character="monster"
      />
    </div>
    <div class="buttons-container" v-if="yourTurn">
      <button
        @click="attack(monster)"
      >
        Attack
      </button>
      <button
        @click="special(monster)"
      >
        Special Attack
      </button>
      <button
        @click="heal(player)"
      >
        Heal
      </button>
    </div>

  </div>
</template>

<script>
import StyledHeader  from './components/StyledHeader.vue';
import Character from './components/Character.vue'
export default {
  name: "App",
  data() {
    return {
      player: {
        name: 'wee little adventuring lad',
        health: 100,
        maxHealth: 100
      },
      monster: {
        name: 'cthulu the lord of the underworld',
        health: 150,
        maxHealth: 150
      },  
      gameFinished: false,
      yourTurn: true,

    }
  },
  components: {
    StyledHeader,
    Character,
  },
  methods: {
    random(min,max){
      return Math.floor(Math.random()*(max-min+1)+min);
    },
    attack( victim ){
      const damage = this.random(1,10)
      this.dealDamage(victim, damage)
    },
    special( victim ){
      const damage = this.random(7,25)
      this.dealDamage(victim, damage)
    },
    heal( recipient ){
      recipient.health += this.random(1,10)
      this.finishTurn()
    },
    dealDamage( victim, damage){
      if( victim.health >= damage ){
        victim.health -= this.random(1,10)
      } else {
        victim.health = 0 
        this.gameFinished = true
      }
      this.finishTurn()
    },
    finishTurn(){
      if(this.yourTurn === true){
        this.yourTurn = false
        setTimeout(()=>{
          this.attack(this.player)
          this.yourTurn = true
        }, 1000)
      }

      
    }
  }
};
</script>

<style>
body {
  padding: 0px;
  margin: 0px;
  border: 0px;
}
.characters-container{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0 100px 0 100px;
}
button{
  width: 300px;
}
.buttons-container{
  display: flex;
  justify-content: center;
}
</style>
