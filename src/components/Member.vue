<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
    name: String,
    image: String,
    special: {
        type: Boolean,
        default: false
    },
    info: {
        type: Array as () => string[],
        default: () => []
    }

});

const isHovered = ref(false);
const isModalVisible = ref(false);

function handleMouseover() {
    isHovered.value = true;
};

function handleMouseleave() {
    isHovered.value = false;
};

function openModal() {
    isModalVisible.value = true;
}

function closeModal() {
    isModalVisible.value = false;

}


</script>

<template>
    <div class="m-wrapper" @mouseover="handleMouseover" @mouseleave="handleMouseleave" @click="openModal">
        <transition name="fade">
            <h1 v-show="isHovered">{{ props.name }}</h1>
        </transition>   
        <img :src="props.image" :class="props.special ? ['m-img-special','flip'] : 'm-img'" alt="Member image" />
    </div>
    <transition name="fade">
        <div v-show="isModalVisible" id="mModal" class="modal">
            <div class="modal-content">
                <span @click="closeModal" class="close">x</span>
                <div class="modal-body">
                    <img :src="props.image" class="p-img"/>
                    <div class="m-info" v-if="props.info.length > 0">
                        <ul>
                            <li><strong>Nombre:</strong> {{ props.info[0] }}</li>
                            <li><strong>Género:</strong> {{ props.info[1] }}</li>
                            <li><strong>Cumpleaños:</strong> {{ props.info[2] }}</li>
                            <li><strong>Especie:</strong> {{ props.info[3] }}</li>
                            <li><strong>Comida favorita:</strong> {{ props.info[4] }}</li>
                            <li><strong>Pasatiempos:</strong> {{  props.info[5] }}</li>
                            <li><strong>Dato freak:</strong> {{ props.info[6] }}</li>
                        </ul>
                    </div>
                    <div class="m-info" v-else>
                        <h1>En  construcción</h1>
                        <h1>(╯°□°）╯︵ ┻━┻</h1>
                    </div>
                </div>
            </div>
        </div>
    </transition>
   
</template>

<style scoped>

@media (width < 1128px) {
  .m-info {
    margin-top: 0;

  }
}
@media (width >= 1128px) {
  .m-info {
    margin-top: 200px;
    font-size:3vh;
  }
}

@media (width <= 425px) {
    .p-img {
        width: 70%;
    }
} 


@media (width > 425px) {
    .p-img {
        width: 700px;
    }
} 

.m-info {
    font-size:3vh;
}


.modal-body {
  display: flex;
  flex-wrap: wrap; 
  align-items: flex-start;
}

.modal-body img {
  flex: 1 1 300px;
}

.modal-body .m-info {
  flex: 1 1 300px;
}

.modal {
  position: fixed; 
  z-index: 1; 
  padding-top: 100px; 
  left: 0;
  top: 0;
  width: 100%; 
  height: 100%; 
  overflow: auto; 
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
    max-width: 360px;
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
