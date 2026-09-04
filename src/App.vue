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
import chunniFmUlr from '@/assets/img/chunnifm.gif';
import rcsUrl from '@/assets/img/rcs.jpg';
import vtubeandoLogo from '@/assets/img/vtubeandologo.png';
import External from './components/External.vue';

const gikkoInfo = ['Gikko Apellido Pun', 'Hombre', '05 de Enero', 'Tigre', 'Ramen', 'Cantar, Jugar y Wargaming Tabletop', 'Se come el completo desde arriba'];
const retniwInfo = ['Retniw', 'Shonen, Slice of life', '13 de Noviembre', 'Pingüino', 'Sandwiches', 'Dibujar y jugar', 'Fui amigo de Ariana Grande en Habbo Hotel'];
const nanaInfo = ['Nana', 'Esqueleto', '14 de Enero', 'Esqueleto', 'Fideos con crema', 'Leer, jugar juegos :B', 'Tiene un cuadro de patos'];
const harpuiaInfo = ['Harpuia', 'Masculino', '04 de Agosto', 'Rana Greninja', 'Arroz con pollo', 'Videojuegos, coleccionar figuras, coleccionar consolas retro', 'Uso el pelo largo por Zero (Megaman)'];
const gishiInfo = ['Gishimon', 'Narrativo', '15 de Mayo', 'Dragon Hikki', 'Churrasco Chacarero', 'Dibujar, juego, procastinar, tirar blasfemias a mis amiguitos', 'Me gane una sandwichera en un sorteo'];
const pupaInfo = ['Pupa', 'Agénero', '24 de Julio', 'Androide', 'Arroz con huevo', 'Cantar, rabiar, dibujar', 'Se encontró en territorio enemigo en contra de su voluntad'];

const chunniFmInfo = "En ChunniFM buscamos darle una vetana de exposición al talento de la comunidad latina, al puro estilo de un programa de radio.";
const chunniFmHorario = "20:30 hrs Chile";

const rcsInfo = "En Retro Chunni Show buscamos explorar los juegos del pasado y redescubrir las joyitas que se ocultan allí."
const rcsHorario = "20:30 hrs Chile";

const ascii = ["                                        ++*+                                                        ", 
"                                  ###%@@@@@@@@@%#                                                   ",
"                                #%@@@%*+    +*%@@@#                                                 ",
"                              *%@%*             #@@@#                                               ",
"                             *%%*             *+ #@@%                                               ",
"                             #%+  #%#*      #@@@# *@@#                                              ",
"                            +## +#@@@@*   *%@#+@@*%@@%                         que                  ",
"                            *%#+%@#:*@@# *%@+..#@@@@@@%                      mirai                  ",
"                           #@@@%@%-..*@%*%%-....#@@@@@@*                        ctm                 ",
"                           @@@@@%-....#@@%:.....:#%*@%*                                             ",
"                           @@@@@=......:-..........=#@@@@%*                                         ",
"                       ##@@@%+::.......................-*@@@@#                                      ",
"                     %@@@#-...............................:+@@@%#                                   ",
"                   #@@@*.....................................-#@@@#                                 ",
"                 #@@@*.........................................:#@@%                                ",
"                %@@%:............................................:%@@#                              ",
"              #@@@+..................::*%+.........................+@@*                             ",
"             #@@@:..................+@@%@#.......::.................-@@%                            ",
"            #@@@:..............=%%:.=%#+@#....:#%#-............-%@@@@@@@*                           ",
"           #@@%:.:-+-..........=%%:.:%%+@%....-%@@#:..........#@@+::::+@%*                          ",
"           %@@*#%%#%@*...............#%+@%:.................:%@#-:::::-%@#                          ",
"          *@@@#+==-=@%:..............*@*@%:.................*@#:::::::=#@%                          ",
"          #@@+-----=#@+..............=@#@%:................:%@+:::::-%%#@@*                         ",
"         *%@@=----==+@%:.............:%#@%:.................#@*:::::=@%:%@*                         ",
"         #@@@=---=*@@@@+..............#%%%:.................-@@#:::::#@%%@*                         ",
"         +%@@=--=%@@-.................+@@%:...................#@@+::::+@@@*                         ",
"          #@@+--+@@:..................:%@%:............*%*:....=@@+::::#@#                          ",
"          *%@%==+@@+.....-+-...........*@#..........:+%%*%@%#**#@@=:::-@@%    #%@@@@@@%%            ",
"           %@@%==*@@@%%@@@@@=..........-%*.........:#@#:::-+#%%#+::::-@@%    #@@*===+%@@%           ",
"            %@@%===#%%%%#=#@@-......................-%@#-:::::::::::-%@#    *%@=======+@@#          ",
"             %@@@+=-------=#@@-......................:#@@@*=----::-%@@*     *@%========%@%          ",
"              #@@@@*=-----==*@#.........................-#@@@@@@%@@@#       #@@#======+@@%          ",
"                #%@@@@*==+%@@*:.............................+%@@%#*         #%@@@@#**%@@@           ",
"                  #%%@@@@@@#:.........................:=*%@@@%#             %@+=*%@@@@%%            ",
"                      #%%%@@@@@%#*-................=@@@@@@#                *@%=+@@%#                ",
"                           *#%%*-....................::=*@@@%              %@*%@@%                  ",
"                         *#%#:............................-%@%#           #@@@@%                    ",
"                        *%%=.........................:::::-+@@%           %@@*                      ",
"                        #@+.........................#@@@@@@@%#         *%@@%*                       ",
"                        *@%*+*#%%@@%:...............:%@*            *%@@@##                         ",
"                         ########*@%:......::........#@#    #+*%%@@@@%%#                            ",
"                                 *@@-.....-@@*.......+@%%@@@@@@%%%##                                ",
"                                 %@@=.....*@@@#:.....+@#                                            ",
"                                  %@*....:%%*%@@-....+@#                                            ",
"                                  %@@:...+@#  %@@*...#@#                                            ",
"                                   %@*..:%@#   #%@@@@@#                                             ",
"                                   #@@=:%@#      #####                                              ",
"                                    #%@@@#                                                          ",
"                                      ++                                                            "];

for(let i = 0; i < ascii.length; i++) {
  console.log(ascii[i]);
}

</script>

<template>
  <header>
    <div class="h-wrapper">
      <img alt="Logo de Chunni Studio" class="logo" src="./assets/img/logo.png" width="40%"/>
      <br>
      <h1>Somos Chunni Studio, un grupo que se dedica a crear contenido y crear espacios donde compartir</h1>
    </div>
  </header>

  <main>
    <div class="c-wrapper">
      <Member name="Gikko" :image="gikkoPngUrl" :info="gikkoInfo"/>
      <Member name="Gishi" :image="gishiPngUrl" :info="gishiInfo"/>
      <Member name="Nana" :image="nanaPngUrl" :info="nanaInfo"/>
      <Member name="Risa" :image="risaPngUrl" />
      <Member name="Hanachi" :image="hanachiPngUrl" />
      <Member name="Pupa" :image="pupaPngUrl" :info="pupaInfo" />
      <Member name="Harpuia" :image="harpuiaPngUrl" :special="true" :info="harpuiaInfo" />
      <Member name="Retniw" :image="retniwPngUrl" :info="retniwInfo"/>
    </div>
  </main>
  <section>
    <div class="a-wrapper">
      <h1>Lo que hacemos</h1>
      <div class="a-subwrapper">
        <Activity name="ChunniFM" :info="chunniFmInfo" :image="chunniFmUlr" :schedule="chunniFmHorario"/>
        <Activity name="Retro Chunni Show" :info="rcsInfo" :image="rcsUrl" :schedule="rcsHorario"/>
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
    <div class="o-wrapper">
      <h1>También visita</h1>
      <div class="l-subwrapper">
        <External :image="vtubeandoLogo" link="https://vtubeando.net"/>
      </div>
    </div>
  </section>
  <footer>
    <p>Creado por <a href="https://harpuia.me" target="_blank">Harpuia 🐸</a></p>
  </footer>
</template>

<style scoped>
  
  .h-wrapper, .a-wrapper, .l-wrapper, .o-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem 0;
  }

  .h-wrapper h1, .a-wrapper h1, .l-wrapper h1, .o-wrapper h1 {
    font-size: 50px;
    color: #FEB722;
    -webkit-text-stroke: 15px #12163F;
    paint-order: stroke fill;
    text-align: center;

  }

  .c-wrapper, .a-subwrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
  }

  footer {
    font-size: 16px;
    text-align: center;
    color: #FEB722;
    -webkit-text-stroke: 7px #12163F;
    paint-order: stroke fill;
  }
</style>
