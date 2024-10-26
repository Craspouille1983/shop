<template>
    <div>
        <carousel :items-to-show="1" class="ban" :autoplay="10000" :wrap-around="true" :pause-autoplay-on-hover="true">
            <slide v-for="slide in slides" :key="`slide-${slide.id}`">
                <h1 v-show="slide.title != ''"><span>{{ slide.title }}</span>
                <br v-show="slide.subtitle != ''" /><span v-show="slide.subtitle != ''">{{ slide.subtitle }}</span>
                </h1>
                <figure><img :src="require(`@/assets/${slide.src}`)" alt="slide.alt"></figure>
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
// import { slice } from 'core-js/core/array';

export default {
    name: "carouselHeader",
    data() {
        return {
            slides: [
                {"id": 1, "title": "Dark Soul 2", "src": 'dark_soul_2/ds2_game-thumbnail.jpg', "alt": "Dark Souls 2" },
                {"id": 2, "title": "Dragon Ball Daïma", "src": 'dragon_ball/db_1.jpg', "alt": "Goku heureux" },
                {"id": 3, "title": "Dragon Quest", "src": 'dragon_quest/daï.jpg', "alt": "Daï préparant un avan strash", 'subtitle': "La légende de Daï" },
                {"id": 4, "title": "Ratchet & Clank", "src": 'ratchet_&_clank/th.webp', "alt": "ratchet & clank en position d'attaque" },
            ],
        }
    },
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation
    }

}
</script>

<style scoped>
.ban {
    top: 0;
    width: 100vw;
    height: 100vh;
    position: relative;
}

.ban li h1 {
    font-family: "Orbitron", sans-serif;
    font-weight: bold;
    font-optical-sizing: auto;
    width: fit-content;
    height: fit-content;
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    color: #fff;
    margin: auto auto;
    font-size: 6em;
    perspective: 1000px;
    font-weight: bolder;
    text-shadow: .025em .015em 0 rgba(0, 0, 0, .75);
}

.ban h1 span {
    display: inline-block;
    transform-origin: center;
    transform: rotate3d(5, 1, -1, 49deg) perspective(10000px);
}

figure {
    width: 100vw;
    height: 100vh;
}

figure img {
    width: 100%;
}
</style>