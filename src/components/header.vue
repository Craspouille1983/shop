<template>
    <nav>
        <figure><img src="../assets/crasp_2_logo.png" alt="logo"></figure>
        <div class="burger"><span></span><span></span><span></span></div>
        <ul v-for="item in itemsNav" :key="`menu-${item.id}`" @error="console.log(item)">
            <li>
                <a :href="item.menuUrl">
                    <!-- Glitch effect -->
                    <span aria-hidden="true">{{ item.menu }}</span>
                    {{ item.menu }}
                    <span aria-hidden="true">{{ item.menu }}</span>
                    <!-- Glitch effect -->
                </a>
            </li>
        </ul>
    </nav>
</template>

<script>

export default {
    name: "headerNav",
    data() {
        return {
            itemsNav: [
                { "id": 1, "menu": 'Accueil', "menuUrl": '/accueil' },
                { "id": 2, "menu": 'Qui sommes-nous ?', "menuUrl": '/about' },
                { "id": 3, "menu": 'Nouveautés', "menuUrl": '/news' }
            ]
        }
    }
}

</script>

<style scoped>
.burger {
    max-width: 3em;
}

.burger span {
    display: inline-block;
    height: .3em;
    width: 3em;
    color: #fff;
}

nav {
    background: rgba(3, 3, 3, .95);
    position: sticky;
    display: flex;
    justify-content: space-between;
    align-items: center;
    top: 0;
    width: 100vw;
    height: 8.5ex;
    padding: .75rem 4rem;
    z-index: 10;
}

nav figure {
    height: 100%;
    filter: contrast(1.75);
}

nav figure img {
    height: 100%;
    object-fit: cover;
}

nav ul {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

nav ul li {
    list-style: none;
}

nav ul li a {
    font-family: "Climate Crisis", sans-serif;
    font-variation-settings: "YEAR" 2012;
    font-weight: bold;
    font-optical-sizing: auto;
    color: #fff;
    text-decoration: none;
}
</style>