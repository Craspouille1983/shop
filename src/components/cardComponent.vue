<template>
    <div class="card">
        <div class="card-header">
            <figure><img :src="require(`@/assets/${src}`)" :alt="descriptionImg"></figure>
        </div>
        <div class="card-bottom">
            <h3>{{ title }}</h3>
            <p>{{ description }}</p>
            <p>{{ prix }} €</p>
            <butonShop :modelValue="btnText" />
        </div>
    </div>
</template>
<script>
    import butonShop from './btnComposant.vue'
    export default {
        name: 'cardGame',
        components: {
            butonShop,
        },
        props: {
            src: {
                type: URL,
                default: '/crasp_2_logo.png'
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