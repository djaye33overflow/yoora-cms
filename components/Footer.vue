<template>
    <v-footer class="footer">
        <v-container>
            <div>
                <nuxt-link to="/">
                    <v-img class="footer__logo mb-6" src="/yoora.png" alt="home">
                    </v-img>
                </nuxt-link>
                <p class="footer__text">We built an elegant solution.
                    Our team created a fully integrated sales and marketing solution for SMBs</p>
                <div class="footer__socials d-flex justify-space-between mt-6 mb-12">
                    <v-img v-for="(social, idx) in socials" :src="social.file" :key="idx" max-height="24"
                        max-width="24"></v-img>
                </div>
            </div>
            <div>
                <v-row>
                    <v-col v-for="(category, idx) in footerCategories" :key="idx" cols="12">
                        <div>
                            <div class="footer__categories">{{ category.title }}</div>
                            <nuxt-link class="footer__links" v-for="(link, idx) in category.links" :to="link.to"
                                :key="idx">{{ link.name
                                }}</nuxt-link>
                        </div>
                    </v-col>
                </v-row>
            </div>

            <v-divider class="mt-12 mb-6"></v-divider>

            <div class="footer__copy">
                <div>
                    <p class="footer__copy-text mb-7">&copy Copyright 2023 Yoora, Inc</p>
                    <div class="footer__copy-links">
                        <nuxt-link class="footer__copy-link mb-3" to="/terms">Terms of Service</nuxt-link>
                        <nuxt-link class="footer__copy-link mb-3" to="/privacy">Privacy Policy</nuxt-link>
                        <nuxt-link class="footer__copy-link mb-6" to="/cookies">Cookies</nuxt-link>
                    </div>
                    <v-select class="footer__language" hide-details solo flat dense prepend-inner-icon="mdi-web"
                        background-color="header-bg" :items="languages" label="English"
                        append-icon="mdi-chevron-down"></v-select>
                </div>
            </div>
        </v-container>
    </v-footer>
</template>

<script>
export default {
    data() {
        return {
            socials: [
                { file: "/twitter.png", alt: "twitter" },
                { file: "/facebook.png", alt: "facebook" },
                { file: "/linkedin.png", alt: "linked in" }
            ],
            footerCategories: [
                { title: "Company", links: [{ name: "About", to: "/about" }, { name: "Pricing", to: "/pricing" }, { name: "Jobs", to: "#" }, { name: "Blog", to: "#" }, { name: "Careers", to: "#" }] },
                { title: "Product", links: [{ name: "Sales software", to: "#" }, { name: "Features", to: "#" }, { name: "Privacy and security", to: "#" }, { name: "Marketplace", to: "#" }, { name: "Status", to: "#" }, { "name": "API", to: "#" }] },
                { title: "Discover", links: [{ name: "Partner Program", to: "#" }, { name: "Get our newsletter", to: "#" }, { name: "Sale Pipeline Course", to: "#" }, { name: "What is CRM?", to: "#" }, { name: "CRM Comparison", to: "#" }, { name: "Resources", to: "#" }] },
                { title: "Help Center", links: [{ name: "Community", to: "#" }, { name: "Knowledge Base", to: "#" }, { name: "Academy", to: "#" }, { name: "Support", to: "#" },] }
            ],
            languages: ["English", "Spanish"]
        }
    }
}
</script>

<style lang="scss" scoped>
.footer {
    padding-top: 7.4rem;

    &__logo {
        max-width: 9.63rem;
        max-height: 2rem;
    }

    &__text {
        font-weight: 400;
        font-size: 1.4rem;
        line-height: 2.4rem;
        color: #404040;
    }

    &__socials {
        cursor: pointer;
        width: 10.4rem;
    }

    &__categories {
        font-weight: 700;
        font-size: 1.6rem;
        line-height: 2.2rem;
    }

    &__links {
        display: block;
        color: #000;
        font-weight: 400;
        font-size: 1.4rem;
        line-height: 3.4rem;
        letter-spacing: 0.02rem;
        text-decoration: none;
    }

    &__links:hover {
        color: #00cc61;
    }

    &__copy-link {
        display: block;
        color: #000;
        font-weight: 400;
        font-size: 1.4rem;
        line-height: 1.9rem;
        letter-spacing: 0.02rem;
        text-decoration: none;
    }

    &__copy-link:hover {
        color: #00cc61;
    }

    &__copy-text {
        font-weight: 400;
        font-size: 1.4rem;
        line-height: 1.9rem;
        letter-spacing: .02rem;
    }


    &__language {
        font-weight: 500;
        font-size: 1.4rem;
        line-height: 1.9rem;
        letter-spacing: 0.02rem;
        width: 13rem;
    }
}
</style>