<script setup lang="ts">
import Member from './components/Member.vue';
import Activity from './components/Activity.vue';
import Network from './components/Network.vue';
import gikkoPngUrl from '@/assets/img/chibigikko.png';
import gishiPngUrl from '@/assets/img/chibigishi.png';
import nanaPngUrl from '@/assets/img/chibinana.png';
import risaPngUrl from '@/assets/img/chibirisa.png';
import hanachiPngUrl from '@/assets/img/chibihanachi.png';
import pupaPngUrl from '@/assets/img/chibiupa.png';
import harpuiaPngUrl from '@/assets/img/harpuia_chibi_2.png';
import retniwPngUrl from '@/assets/img/retni_chibi.png';

console.log("Que mirai ctm");

</script>

<template>
  <header>
    <div class="h-wrapper">
      <img alt="Logo de Chunni Studio" class="logo" src="./assets/img/logo.png" width="40%"/>
      <br>
      <h1>Hola soy un texto de prueba</h1>
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
      <Member name="Harpuia" :image="harpuiaPngUrl" :special="true" />
      <Member name="Retniw" :image="retniwPngUrl" />
    </div>
  </main>
  <section>
    <div class="a-wrapper">
      <h1>Actividades</h1>
      <div class="a-subwrapper">
        <Activity name="ChunniFM"/>
        <Activity name="Retro Chunni Show"/>
      </div>
    </div>
  </section>
  <section>
    <div class="l-wrapper">
      <h1>Redes</h1>
      <div class="l-subwrapper">
        <Network link="https://www.twitch.tv/chunnistudio/" icon="fa-twitch"/>
        <Network link="https://www.youtube.com/@ChunniStudio" icon="fa-square-youtube"/>
        <Network link="https://x.com/ChunniStudio" icon="fa-x-twitter"/>
        <Network link="https://bsky.app/profile/chunnistudio.bsky.social/" icon="fa-bluesky"/>
        <Network link="https://discord.chunni.studio" icon="fa-discord"/>

      </div>
    </div>
    
  </section>
  <footer>
    <p>Creado por <a href="https://harpuia.me" target="_blank">Harpuia 🐸</a></p>
  </footer>
</template>

<style scoped>
  
  .h-wrapper, .a-wrapper, .l-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem 0;
  }

  .h-wrapper h1, .a-wrapper h1, .l-wrapper h1 {
    font-size: 50px;
    color: #FEB722;
    -webkit-text-stroke: 15px #12163F;
    paint-order: stroke fill;

  }

  .c-wrapper, .a-subwrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin: 0 auto;
  }

  footer {
    font-size: 16px;
    text-align: center;
    color: #FEB722;
    -webkit-text-stroke: 7px #12163F;
    paint-order: stroke fill;
  }
</style>
