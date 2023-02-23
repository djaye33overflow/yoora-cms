<template>
    <section class="action primary-blue">
        <div>
            <div>
                <h3 class="action__title white--text mb-4">Ready to supercharge your business?</h3>
                <p class="action__text white--text">Ask about Yoora products, pricing, implementation, or anything else. Our
                    highly
                    trained reps are standing
                    by, ready to help.</p>
            </div>
            <div class="text-center">
                <v-btn class="action__btn white elevation-0" large light to="#" nuxt>Try for Free
                    <v-icon right>mdi-chevron-right</v-icon>
                </v-btn>
                <p class="action__access-text white--text mt-6">Full access. No credit card required.</p>
            </div>
        </div>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.action {
    background-image: url("/Shape-green-bg.png"), url("/Shape-bg.png");
    background-size: 130%, 110%;
    background-position: bottom center, bottom center;
    background-repeat: no-repeat, no-repeat;
    padding: 7.2rem 2.4rem;

    &__title {
        font-weight: 700;
        font-size: 3.6rem;
        line-height: 4.6rem;
        letter-spacing: -0.05rem;
    }

    &__text {
        font-weight: 500;
        font-size: 1.8rem;
        line-height: 2.8rem;
        opacity: .72;
        margin-bottom: 18rem;
    }

    &__btn {
        font-weight: 700;
        font-size: 1.8rem;
        line-height: 2.4rem;
        letter-spacing: -0.025rem;
        text-transform: unset;
    }

    &__access-text {
        font-weight: 500;
        font-size: 1.4rem;
        line-height: 1.9rem;
    }
}
</style>