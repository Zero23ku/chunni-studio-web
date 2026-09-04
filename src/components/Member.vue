<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    name: String,
    image: String,
    special: {
        type: Boolean,
        default: false
    }

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
        <transition name="fade">
            <h1 v-show="isHovered">{{ props.name }}</h1>
        </transition>   
        <img :src="props.image" :class="props.special ? ['m-img-special','flip'] : 'm-img'" alt="Member image" />
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
    flex: 0 0 360px;
}

.m-wrapper h1 {
    font-size: 60px;
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

.m-img-special {
    position: absolute;
    top: -366px;
    right: -323px;
    width: 700px; 
}


.fade-enter-active, .fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

.flip {
    transform: scale(-1,-1);
}
    
</style>
