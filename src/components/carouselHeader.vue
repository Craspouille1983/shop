<template>
    <div>
        <carousel :items-to-show="1" class="ban" :autoplay="10000" :wrap-around="true" :pause-autoplay-on-hover="true">
            <slide v-for="slide in slides" :key="`slide-${slide.id}`">
                <h2 v-show="slide.title != ''"><span>{{ slide.title }}</span>
                </h2>
                <br v-show="slide.subtitle != ''" />
                <h3 v-show="slide.subtitle != ''">{{ slide.subtitle }}</h3>
                <figure><img :src="require(`@/assets/${slide.src}`)" alt="slide.alt"></figure>
                <butonShop :model-value="slide.text_button" />
            </slide>

            <template #addons>
                <navigation />
                <pagination />
            </template>
        </carousel>
    </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
import butonShop from './btnComposant.vue';
// import { slice } from 'core-js/core/array';

export default {
    name: "carouselHeader",
    data() {
        return {
            slides: [
                { "id": 1, "title": "Dark Soul 2", "src": 'dark_soul_2/ds2_game-thumbnail.jpg', "alt": "Dark Souls 2", "text_button": "Commander" },
                { "id": 2, "title": "Dragon Ball Daïma", "src": 'dragon_ball/db_1.jpg', "alt": "Goku heureux", "text_button": "Précommander" },
                { "id": 3, "title": "Dragon Quest", "src": 'dragon_quest/daï.jpg', "alt": "Daï préparant un avan strash", 'subtitle': "La légende de Daï", "text_button": "Où jouer ?" },
                { "id": 4, "title": "Ratchet & Clank", "src": 'ratchet_&_clank/th.webp', "alt": "ratchet & clank en position d'attaque", "text_button": "Commander" },
            ],
        }
    },
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation,
        butonShop,
    }

}
</script>

<style scoped>
.ban {
    top: 0;
    width: 100vw;
    height: 100vh;
    position: relative;
    overflow: hidden;
}

.ban li h2 {
    font-family: "Climate Crisis", sans-serif;
    font-variation-settings: "YEAR" 1983;
    font-optical-sizing: auto;
    width: calc(100% - 70%);
    text-align: left;
    position: absolute;
    left: 1em;
    color: #fff;
    font-size: 4em;
    font-weight: bolder;
    text-shadow: .025em .015em 0 rgba(0, 0, 0, .75);
    z-index: 1;
}

.ban h2 span {
    display: inline-block;
    transform-origin: center;
}

.ban li h3 {
    font-family: "Pangolin", sans-serif;
    font-weight: bold;
    font-optical-sizing: auto;
    width: fit-content;
    height: fit-content;
    position: absolute;
    left: 4rem;
    margin-bottom: -11ex;
    color: #fff;
    font-size: 2em;
    z-index: 1;
}

.ban button {
    position: absolute;
    top: 50%;
    right: 4rem;
}

figure {
    width: 100%;
    height: 100%;
    filter: brightness(.75);
}

figure img {
    width: 100%;
}
</style>