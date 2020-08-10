<template>
    <div class="character-container">
        <LoadingBar
            :totalHealth="character.maxHealth"
            :currentHealth="character.health"
        />
        <h1>{{character.name}}</h1>
    </div>
    
</template>

<script>
import LoadingBar from './LoadingBar'
export default {
    props: {
        character: {
            deep:true,
        }
    },
    components:{
        LoadingBar
    }
}
</script>

<style scoped>
    .character-container{
        margin: 30px;
    }
    
</style>