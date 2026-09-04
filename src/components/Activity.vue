<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    name: String,
    info: String,
    image: String,
    schedule: String
});

const isHovered = ref(false);
const isModalVisible = ref(false);

function handleMouseover() {
    isHovered.value = true;
};

function handleMouseleave() {
    isHovered.value = false;
};

function showModal() {
    isModalVisible.value = true;
}

function closeModal() {
    isModalVisible.value = false;
}


</script>

<template>
    <div class="m-wrapper" @mouseover="handleMouseover" @mouseleave="handleMouseleave" @click="showModal">
        <h1 :class="{ zoomed: isHovered}"">{{ props.name }}</h1>
    </div>
    <transition name="fade">
        <div v-show="isModalVisible" id="mModal" class="modal">
            <div class="modal-content">
                <span @click="closeModal" class="close">x</span>
                <div class="modal-body">
                    <img :src="props.image" class="a-img"/>
                    <div class="m-info">
                        {{  props.info }}
                        <ul>
                            <li><strong>Horario:</strong> {{ props.schedule }}</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </transition>
   
</template>

<style scoped>


@media (width <= 820px) {
    .a-img {
        width: 70%;
    }
} 


@media (width > 820px) {
    .a-img {
        width: 500px;
    }
} 


@media (width < 1128px) {
  .m-info {
    margin-top: 0;

  }
}
@media (width >= 1128px) {
  .m-info {
    margin-top: 180px;
    font-size:3vh;
  }
}

.m-info {
    font-size:3vh;
}

.m-info{
    margin-left: 10px;
}

.modal-body {
  display: flex;
  flex-wrap: wrap; 
  align-items: flex-start;
}

.modal-body .m-info {
  flex: 1 1 300px;
}

.modal {
  position: fixed; 
  z-index: 1; 
  padding-top: 10px; 
  left: 0;
  top: 0;
  width: 100%; 
  height: 100%; 
  overflow: hidden; 
  background-color: rgb(0,0,0); 
  background-color: rgba(0,0,0,0.4); 
}

.modal-content {
  background-color: #fefefe;
  margin: auto;
  padding: 10px;
  border: 1px solid #888;
  width: 90%;
  overflow-y: scroll;
}

.close {
  color: #aaaaaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}

.m-wrapper {
    background-color: white;
    height: 200px;
    width: 360px;
    overflow: hidden;
    position: relative;
    display: flex;
    align-items: center;
    flex: 0 0 360px;
}

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
