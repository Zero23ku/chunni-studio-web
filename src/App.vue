<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue'
//import TheWelcome from './components/TheWelcome.vue'
import Member from './components/Member.vue';
import gikkoPngUrl from '@/assets/img/chibigikko.png';
import gishiPngUrl from '@/assets/img/chibigishi.png';
import nanaPngUrl from '@/assets/img/chibinana.png';
import risaPngUrl from '@/assets/img/chibirisa.png';
import hanachiPngUrl from '@/assets/img/chibihanachi.png';
import pupaPngUrl from '@/assets/img/chibiupa.png';
import harpuiaPngUrl from '@/assets/img/harpuia_chibi_2.png';
import retniwPngUrl from '@/assets/img/retni_chibi.png';


</script>

<template>
  <header>
    <div class="h-wrapper">
      <img alt="Logo de Chunni Studio" class="logo" src="./assets/img/logo.png" width="40%"/>
      <br>
      <p>Hola soy un texto de prueba</p>
    </div>
  </header>

  <main>
    <div class="c-wrapper">
      <Member name="Gikko" :image="gikkoPngUrl" />
      <Member name="Gishi" :image="gishiPngUrl" />
      <Member name="Nana" :image="nanaPngUrl" />
      <Member name="Risa" :image="risaPngUrl" />
      <Member name="Hanachi" :image="hanachiPngUrl" />
      <Member name="Pupa" :image="pupaPngUrl" />
      <Member name="Harpuia" :image="harpuiaPngUrl" />
      <Member name="Retniw" :image="retniwPngUrl" />
    </div>
  </main>
</template>

<style scoped>
  .c-wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin: 0 auto;
  }
</style>
