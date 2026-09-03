<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    name: String,
    image: String

});

const isHovered = ref(false);

function handleMouseover() {
    isHovered.value = true;
    console.log(isHovered.value);
};

function handleMouseleave() {
    isHovered.value = false;
    console.log(isHovered.value);

};


</script>

<template>
    <div class="m-wrapper" @mouseover="handleMouseover" @mouseleave="handleMouseleave">
        <transition name="fade">
            <h1 v-show="isHovered">{{ props.name }}</h1>
        </transition>   
        <img class="m-img" :src="props.image" alt="Member image" />
    </div>
   
</template>

<style scoped>
.m-wrapper {
    background-color: white;
    height: 200px;
    width: 360px;
    overflow: hidden;
    position: relative;
    display: flex;
    align-items: center;
    padding-left: 40px;
    flex: 0 0 360px; /* fijo: no crece (0), no encoge (0) */
}

.m-wrapper:hover {
    cursor: pointer;
}

.m-img {
    position: absolute;
    top: -135px;
    right: -355px;
    width: 700px;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
    
</style>
