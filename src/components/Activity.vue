<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    name: String,
});

const isHovered = ref(false);

function handleMouseover() {
    isHovered.value = true;
};

function handleMouseleave() {
    isHovered.value = false;
};


</script>

<template>
    <div class="m-wrapper" @mouseover="handleMouseover" @mouseleave="handleMouseleave">
        <h1 :class="{ zoomed: isHovered}"">{{ props.name }}</h1>
    </div>
   
</template>

<style scoped>

.m-wrapper {
    background-color: white;
    height: 200px;
    width: 360px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    flex: 0 0 360px;
    text-align: center;
}

.m-wrapper h1 {
    font-size: 40px;
}

.m-wrapper:hover {
    cursor: pointer;
}

h1 {
  transform: scale(1);
  transition: transform 0.2s ease-in-out;
}

h1.zoomed {
  transform: scale(1.2);
}
    
</style>
