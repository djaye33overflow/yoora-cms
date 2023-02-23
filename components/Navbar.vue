<template>
    <nav class="nav header-bg">
        <v-app-bar class="elevation-0 header-bg">
            <v-container class="d-flex align-center">
                <nuxt-link to="/">
                    <v-img class="nav__logo" src="/yoora.png" alt="home">
                    </v-img>
                </nuxt-link>
                <div class="nav__links hidden-sm-and-down">
                    <nuxt-link class="nav__link-item" v-for="(link, idx) in navLinks" :to="link.to" :key="idx">{{
                        link.name }}</nuxt-link>
                </div>
                <v-spacer></v-spacer>
                <div class="nav__btns hidden-sm-and-down">
                    <v-btn class="nav__btn white mr-4 elevation-0" to="/login" nuxt>Log In</v-btn>
                    <v-btn class="nav__btn primary-blue white--text elevation-0" to="/try" nuxt>Try for Free</v-btn>
                </div>
                <v-app-bar-nav-icon class="nav__menu-icon hidden-md-and-up"></v-app-bar-nav-icon>
            </v-container>
        </v-app-bar>
</nav>
</template>

<script>

export default {
    data() {
        return {
            navLinks: [{ name: "Product", to: "/product" }, { name: "Pricing", to: "/pricing", }, { name: "Company", to: "/company" }, { name: "Resources", to: "/resources" }, { name: "Contact", to: "/contact" }],
        }
    }
}
</script>

<style lang="scss" scoped>
.nav {

    &__logo {
        max-width: 9.63rem;
        max-height: 2rem;
    }

    &__links {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 33rem;
        margin-left: 9rem;
    }

    &__link-item {
        // font-weight: 500;
        font-size: 1.4rem;
        line-height: 1.9rem;
        color: #000;
        text-decoration: none;
    }

    &__link-item:hover {
        // nuxt link hover hard coded - doesn't seem to work with vuetify theme colors in nuxt.config.js
        color: #00cc61;
    }

    &__btn {
        font-weight: 700;
        font-size: 1.4rem;
        line-height: 1.9rem;
        text-transform: unset;
    }
}
</style>