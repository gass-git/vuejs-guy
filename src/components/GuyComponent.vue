<script setup>
	import {defineProps, computed} from 'vue'
  
  const 
    props = defineProps({position: String, feels: String}),
    position = computed(() => props.position);
</script>

<template>
    <section class="guy">
      <div v-if="props.feels === 'happy'">
        😀
      </div>
      <div v-else-if="props.feels === 'smart'">
        👽
      </div>
      <div v-else-if="props.feels === 'sad'">
        😩
      </div>
      <div v-else>
        😐	
      </div>
      <div>
        -|-
      </div>
      <div>
        / \
      </div>
  	</section>
</template>

<style>
	.guy{
  	display:grid;
    position:relative;
    left:v-bind(position);
    width:100vw;
    grid-template-columns: auto;
    grid-template-rows:auto;
    width:40px;
  }
  .guy > div{
   	display:grid;
    position:relative;
    place-items:center;
  }
</style>
