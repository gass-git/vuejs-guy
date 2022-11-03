<script setup>
	import {ref, computed} from 'vue'
 	import GuyComponent from '@/components/GuyComponent.vue'
  
	const 
  	pixels = ref(100),
  	position = computed(() => pixels.value + 'px'),
    inputTxt = ref('');
  
	function move(direction){
  	if(direction === 'left')
      pixels.value -= 10;
    else
      pixels.value += 10;
  }
</script>

<template>
  <button v-on:click="move('left')">
    move left
  </button>

  <button v-on:click="move('right')">
    move right
  </button>
  
  <label>Vue.js guy feels: </label><input v-model="inputTxt" />

  <div id="area">
    <GuyComponent 
      v-bind:position="position" 
      v-bind:feels="inputTxt" 
    />
  </div>
</template>

<style scoped>
  button{
    margin:10px;
  }
  #area{
    margin-top:50px;
    width:100%;
    border-bottom:1px solid black;
  }
</style>
