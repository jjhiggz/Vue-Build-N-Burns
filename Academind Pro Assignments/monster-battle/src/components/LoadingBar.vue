<template>
    <div
        class="loading-container"
        :style="{
            width: 300 + 'px',
            height: 40 + 'px',
            backgroundColor: 'red',
        }"
    >
        <div
            class="loading-progress"
            :style="{
            width: Math.round( this.currentHealth / this.totalHealth * 300).toString() + 'px',
            height: 100 + '%',
            backgroundColor: 'green',
        }"
        >
        
        </div>
    </div>
</template>

<script>
export default {
    name: 'LoadingBar',
    props: {
        totalHealth: Number,
        currentHealth: Number,
    }
}
</script>