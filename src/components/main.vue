<template>
    <section class="card-container">
        <div v-for="slide in slides" :key="`card-${slide.id}`">
            <cardComponent :title="slide.title" :src="slide.src" :descriptionImg="slide.alt" :description="slide.description" :prix="slide.price" :btnText="slide.text_button"/>
        </div>
    </section>
</template>

<script>
    import cardComponent from './cardComponent.vue';

    export default {
        name: 'mainShop',
        components: {
            cardComponent
        },
    data() {
        return {
            slides: [
                { "id": 1, "title": "Dark Soul 2", "src": 'dark_soul_2/ds2_game-thumbnail.jpg', "alt": "Dark Souls 2", "description": "Dark Souls II est un jeu vidéo d'action-RPG développé par From Software, se déroulant dans un univers sombre où le joueur explore le royaume de Drangleic.", "text_button": "Commander", "price": 45.99 },
                { "id": 2, "title": "Dragon Ball Daïma", "src": 'dragon_ball/db_1.jpg', "alt": "Goku heureux", "description": "Quelques mois après la défaite du monstre Buu, nos héros croient le monde débarrassé de la plus grande menace de l'univers. Mais suite à une conspiration sournoise, ils se retrouvent mystérieusement réduits à une taille minuscule", "text_button": "Commander", "price": 74.99 },
                { "id": 3, "title": "Dragon Quest", "src": 'dragon_quest/daï.jpg', "alt": "Daï préparant un avan strash", 'subtitle': "La légende de Daï", "description": "Dragon Quest est un jeu vidéo de rôle (RPG) développé par Chunsoft et publié par Enix, sorti pour la première fois en 1986 sur NES au Japon.", "text_button": "Commander", "price": 43.99 },
                { "id": 4, "title": "Ratchet & Clank", "src": 'ratchet_&_clank/th.webp', "alt": "ratchet & clank en position d'attaque", "description": "Ratchet et Clank est un film d'animation américano-canadien qui suit les aventures d'un jeune mécanicien Lombax, Ratchet, et d'un robot intelligent, Clank.", "text_button": "Commander", "price": 55.00 },
            ],
        }
    },

    }
</script>