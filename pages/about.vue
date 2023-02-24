<template>
    <div>
        <v-container>
            <header>
                <div class="about__header">
                    <h1 class="about__title mb-4">We build bridges between<span>companies and customers</span></h1>
                    <p class="about__subtext">To build software that gives customer-facing teams at small- and medium-sized
                        businesses the ability to
                        create fruitful and enduring relationships with customers.</p>
                </div>
                <v-img src="/about-hero.png" alt=""></v-img>
            </header>
            <main>
                <section>
                    <div>
                        <h2>Together we are strong</h2>
                    </div>
                    <div>
                        <p>Our crew is always getting bigger, but we all work toward one goal: to make sales success not
                            only possible but inevitable for teams everywhere.</p>
                            <p>
                                In 2022, at vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.
                            </p>
                    </div>
                </section>
            </main>
        </v-container>
    </div>
</template>

<script>

export default {

}
</script>

<style lang="scss" scoped>
.about {

    &__header {}

    &__title {
        font-weight: 700;
        font-size: 36px;
        line-height: 46px;
        letter-spacing: -0.5px;
        color: #000;

        & span {
            display: inline-block;
        }
    }

    &__subtext {
        font-weight: 400;
        font-size: 16px;
        line-height: 26px;
        color: #000;
    }
}
</style>