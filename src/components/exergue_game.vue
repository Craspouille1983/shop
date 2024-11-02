<template>
    <div class="exergue-game">
        <div class="left-panel">
            <figure><img :src="require(`@/assets/${src}`)" :alt="descriptionImg"></figure>
        </div>
        <div class="right-panel">
            <div><span></span><span></span></div>
            <div><span></span><span></span></div>
            <h3>{{ title }}</h3>
            <p>{{ description }}</p>
            <a :href="link"></a>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'exergueGames',
        props: {
            src: {
                type: URL,
                default: 'crasp_2_logo.png'
            },
            link: {
                type: URL,
            },
            descriptionImg: {
                type: String,
            },
            title: {
                type: String,
                default: 'Card'
            },
            description: {
                type: String,
                default: 'Lorem ipsum sit amet dolor'
            },
            prix: {
                type: Number,
                default: 0
            },
            btnText: {
                type: String,
            }
        }
    }
</script>