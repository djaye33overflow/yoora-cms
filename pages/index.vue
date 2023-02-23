<template>
  <div>
    <header class="home header-bg pb-6">
      <v-sheet class="header-bg px-2">
        <v-container>
          <v-row>
            <v-col class="home__content-group">
              <div class="home__input-group">
                <div class="home__content header-bg">
                  <h1 class="home__heading">Bringing companies and customers together, anywhere</h1>
                  <p class="home__text mb-8">An awesome & powefull tools for your business, increase business revenue with
                    enterprise-grade links built to
                    acquire and engage cutomers.</p>
                </div>
                <div>
                  <v-card class="home__email-card pa-2 elevation-0">
                    <v-text-field class="home__email-text ma-0 pt-0 mb-2" solo flat placeholder="Enter your email"
                      hide-details dense full-width></v-text-field>
                    <v-btn class="home__email-try-btn accent-green white--text elevation-0 rounded-lg" block>Try for
                      Free</v-btn>
                  </v-card>
                  <p class="home__credit-text mt-3">Full access. No credit card required.</p>
                </div>
              </div>
            </v-col>
            <v-col>
              <figure class="home__graph-container">
                <v-img class="home__graph rounded-lg" src="/graph.png"></v-img>
              </figure>
            </v-col>
            <v-col>
              <p class="home__trusted-text mb-8 mt-6">Trusted by 1,000+ customers</p>
              <v-row class="pr-7">
                <v-col v-for="(path, idx) in imagePaths" :key="idx" col="6" align-self="center">
                  <v-img class="home__customers" :src="path.imagePath" contain></v-img>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-sheet>
    </header>
    <!-- BENEFITS SECTION -->
    <section>
      <v-sheet class="home__benefits primary-blue">
        <v-container class="pa-0">
          <div>
            <h2 class="home__benefits-title white--text mb-4">Here's how Yoora can benefit your business</h2>
            <p class="home__benefits-text pb-8">Build more meaningful and lasting relationships — better understand their
              needs,
              identify new opportunities
              to help, address any problems faster.</p>
          </div>
          <v-row>
            <v-col v-for="(content, idx) in benefitsContent" :key="idx" class="py-2">
              <v-card class="home__benefits-card py-8 px-6 rounded-lg"
                :class="[idx === 0 ? 'accent-gold' : '', idx > 0 ? 'home__cardStyle' : '']" :dark="idx > 0" flat>
                <v-img class="mb-8" :src="content.imagePath" :alt="content.alt" contain height="48" width="42"></v-img>
                <v-divider></v-divider>
                <v-card-title class="home__benefits-card-title px-0">{{ content.title }}</v-card-title>
                <v-card-text class="home__benefits-card-text px-0">{{ content.text }}</v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-sheet>
    </section>
    <main>
      <section>
        <v-container>
          <v-row v-for="(offering, idx) in offeringsContent" :key="idx">
            <v-col cols="12">
              <v-divider class="mb-10 mt-16"></v-divider>
              <v-chip class="accent-gold rounded">{{ offering.badgeText.toUpperCase() }}</v-chip>
              <h3 class="home__offerings-title mt-3">{{ offering.title }}</h3>
              <p class="home__offerings-text my-4">{{ offering.text }}</p>
              <div>
                <div class="d-flex align-start" v-for="(offeringItem, idx) in offering.items" :key="idx">
                  <v-icon color="accent-green" left>{{ offeringItem.icon }}</v-icon>
                  <p class="home__offerings-point">{{ offeringItem.itemText }}</p>
                </div>
              </div>
            </v-col>
            <v-col>
              <v-img :src="offering.imagePath" :alt="offering.alt"></v-img>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <section class="home__testimonials header-bg">
        <v-container>
          <div class="home__testimonials-head">
            <h4 class="home__testimonials-title text-center mb-6">We love our Customers and They love us too</h4>
            <nuxt-link class="home__testimonials-link m-auto" to="#">See all <v-icon color="accent-green"
                small>mdi-chevron-right</v-icon></nuxt-link>
          </div>
          <v-row>
            <v-col v-for="(testimonial, idx) in testimonials" :key="idx">
              <v-img class="mt-11" :src="testimonial.imagePath" :alt="testimonial.alt" height="58" width="58"
                contain></v-img>
              <v-divider class="mb-4 mt-6"></v-divider>
              <p class="home__testimonials-text text-left mb-6">{{ testimonial.testimonialText }}</p>
              <div class="home__testimonials-content text-left d-flex">
                <v-avatar class="mr-3">
                  <img :src="testimonial.avatarPath" alt="" />
                </v-avatar>
                <div>
                  <div class="home__testimonials-user mb-1 font-weight-bold">{{ testimonial.username }}</div>
                  <p class="home__testimonials-position">{{ testimonial.userPosition }}</p>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <section class="home__new">
        <v-container>
          <div>
            <div>
              <h4 class="home__new-title mb-6">What's new at Yoora?</h4>
              <nuxt-link class="home__new-link" to="#">See all <v-icon color="accent-green"
                  small>mdi-chevron-right</v-icon></nuxt-link>
            </div>
            <v-row>
              <v-col v-for="(posts, idx) in whatsNew" :key="idx">
                <div class="home__new-posts-title mt-12">{{ posts.title.toUpperCase() }}</div>
                <v-divider class="my-4"></v-divider>
                <v-img :src="posts.imagePath" :alt="posts.alt"></v-img>
                <div class="home__new-posts-text mb-4">{{ posts.text }}</div>
                <div class="home__new-posts-date"><span>{{ posts.post.date }}</span> by {{ posts.post.by }}</div>
              </v-col>
            </v-row>
          </div>
          <div>
            <div>
              <h4></h4>
              <p></p>
            </div>

          </div>
        </v-container>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  // name: 'IndexPage'
  data() {
    return {
      imagePaths: [
        { imagePath: "/Google.png", alt: "" },
        { imagePath: "atlassian.png", alt: "" },
        { imagePath: "Canon.png", alt: "" },
        { imagePath: "/walmart.png", alt: "" },
        { imagePath: "amazon.png", alt: "" }
      ],
      benefitsContent: [
        { imagePath: "/icon-head.png", alt: "", title: "Lead customers to happiness", text: "Yoora Support helps you provide personalized support when and where customers need it, so customers stay happy." },
        { imagePath: "/icon-laptop.png", alt: "", title: "Support your support", text: "Productive agents are happy agents. Give them all the support tools and information they need to best serve your customers." },
        { imagePath: "/icon-wand.png", alt: "", title: "Grow without growing pains", text: "Our software is powerful enough to handle the most complex business, yet flexible enough to scale with you as you grow." }
      ],
      offeringsContent: [
        {
          badgeText: "sales", title: "Increase company revenue up to 65%", text: "Automate your sales, marketing, and service in one platform. Avoid data leaks and enable consistent messaging.",
          items: [
            { icon: "mdi-check", itemText: "Close more deals with single-page contact management" },
            { icon: "mdi-check", itemText: "Enjoy one-click calling, call scripts and voicemail automation" },
            { icon: "mdi-check", itemText: "Track stages and milestones of your deals to keep the sales process on track" }
          ], imagePath: "/woman-laptop.png", alt: "woman sitting at cafe table on laptop"
        },
        {
          badgeText: "marketing", title: "Marketing Automation", text: "Market like the most successful companies in the world with Agile CRM's marketing automation software. ",
          items: [
            { icon: "mdi-check", itemText: "Marketing workflows with an easy drag-and-drop designer" },
            { icon: "mdi-check", itemText: "Use our templates to create high converting, mobile responsive landing pages" },
            { icon: "mdi-check", itemText: "Integrate social media easily into your marketing campaigns & contact views" }
          ], imagePath: "/phone-mockup.png", alt: "mockup of cell phone"
        },
        {
          badgeText: "service", title: "Help Desk Software", text: "Great customer support separates decent companies from excellent companies. A positive customer support experience is a crucially important piece of the customer journey. ",
          items: [
            { icon: "mdi-check", itemText: "Resolve every issue in the shortest possible time with powerful ticketing features" },
            { icon: "mdi-check", itemText: "Categorize tickets according to the issue and route them to the appropriate group (e.g. sales or support)" },
            { icon: "mdi-check", itemText: "Enjoy at-a-glance views of important data—such as ticket priority—on your dashboard" }
          ], imagePath: "/help-desk.png", alt: "mock up of help desk dashboard"
        }
      ],
      testimonials: [
        { imagePath: "/quote-mark.png", alt: "", testimonialText: "The best thing we love about Yoora is it does two-way sync with Google Apps. It has helped us to better organize and keep everything on track.", avatarPath: "/avatar-lola.png", username: "Lola Ross", userPosition: "Digital Marketing Director" },
        { imagePath: "/quote-mark.png", alt: "", testimonialText: "It has made our sales department more effective and efficient. It's easy to use and it's constantly updated. It's easy to use and it's constantly updated.", avatarPath: "/avatar-daisy.png", username: "Daisy Phelps", userPosition: "Speaker and Author, Lifeiseasy" },
        { imagePath: "/quote-mark.png", alt: "", testimonialText: "Easy to use, reasonably priced, and ensures I don't drop the ball on following up with my leads!", avatarPath: "/avatar-andrew.png", username: "Andrew Wilkins", userPosition: "Managing Director, Nirma Studio" },
      ],
      whatsNew: [
        {
          title: "service", imagePath: "/people-in-a-meeting.png", alt: "people in a meeting", text: "How To Deliver a Successful Product Launch",
          post: { date: "05 Sep 2022,", by: "Joushua Nash" }
        },
        {
          title: "service", imagePath: "man-walking-in-city.png", alt: "business man walking in city", text: "What Makes an Authentic Employee Profile, and Why…",
          post: { date: "07 Sep 2022,", by: "Joushua Nash" }
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
.home {
  &__cardStyle {
    background-color: rgba(255, 255, 255, .04);
  }

  &__heading {
    font-size: 3.6rem;
    line-height: 4.6rem;
    letter-spacing: -0.05rem;
  }

  &__text {
    font-size: 1.6rem;
    line-height: 2.6rem;
    margin-top: 1.6rem;
  }

  &__email-text {
    font-size: 1.6rem;
    line-height: 2.2rem;
    letter-spacing: -0.022rem;

  }

  &__email-try-btn {
    font-size: 1.6rem;
    min-height: 4.8rem;
    line-height: 2.2rem;
    letter-spacing: -0.022rem;
    text-transform: unset;
  }


  &__credit-text {
    font-size: 1.4rem;
    line-height: 1.9rem;
    color: #404040;
  }

  &__graph-container {
    margin-right: -3rem;
  }

  &__graph {
    border: .75rem solid black;
  }

  &__trusted-text {
    font-size: 1.4rem;
    line-height: 1.9rem;
    letter-spacing: -0.0194rem;
  }

  &__customers {
    max-height: 3rem;
    width: 9.5rem;
    margin-bottom: 2.5rem;
  }

  //**** BENEFITS SECTION ****//

  &__benefits {
    padding: 7.2rem 2.4rem;
    margin-bottom: .8rem;
  }

  &__benefits-title {
    font-size: 3.6rem;
    line-height: 4.6rem;
    letter-spacing: -0.05rem;
  }

  &__benefits-text {
    color: #f4f4f4;
    font-size: 1.6rem;
    line-height: 2.6rem;
  }

  &__benefits-card {
    height: 38.3rem;
    min-width: 27.2rem;
    max-width: 37.4rem;

    @media(min-width: 960px) {
      height: 43.9rem;
    }
  }

  &__benefits-card-title {
    font-size: 2rem;
    line-height: 2.7rem;
    letter-spacing: .0375rem;
    word-break: break-word;
  }

  &__benefits-card-text {
    font-size: 1.6rem;
    line-height: 2.6rem;
  }

  //**** OFFERINGS SECTION ****/
  &__offerings-title {
    font-size: 2.4rem;
    line-height: 3.4rem;
    letter-spacing: -0.033rem;
  }

  &__offerings-text {
    font-size: 1.6rem;
    line-height: 2.6rem;
  }

  &__offerings-point {
    font-size: 1.6rem;
    line-height: 2.6rem;
    letter-spacing: .02rem;
  }

  //**** TESTIMONIALS SECTION ****//
  &__testimonials {
    padding: 7.2rem 2.4rem;
    text-align: center;
  }

  &__testimonials-title {
    font-size: 3.6rem;
    line-height: 4.6rem;
    letter-spacing: -0.05rem;
  }

  &__testimonials-link {
    font-size: 2rem;
    line-height: 2.7rem;
    letter-spacing: .04rem;
    text-decoration: none;
    color: #000;
  }

  &__testimonials-text {
    font-weight: 500;
    font-size: 2rem;
    line-height: 3rem;
    letter-spacing: -0.2784px;
  }

  &__testimonials-user {
    font-size: 1.4rem;
    line-height: 1.9rem;
  }

  &__testimonials-position {
    font-size: 1.4rem;
    line-height: 1.9rem;
    color: #404040;
  }

  //**** WHATS NEW SECTION ****//
  &__new {
    padding: 7.2rem 0;
  }

  &__new-title {
    font-size: 3.6rem;
    line-height: 4.6rem;
    letter-spacing: -0.05rem;
  }

  &__new-posts-title {
    font-size: 1.4rem;
    line-height: 1.9rem;
    letter-spacing: .14rem;
    color: #787878;
  }

  &__new-link {
    font-size: 1.6rem;
    line-height: 2.2rem;
    color: #000;
    letter-spacing: .034rem;
    text-decoration: none;
  }

  &__new-posts-text {
    font-weight: 700;
    font-size: 2rem;
    line-height: 3rem;
    letter-spacing: -0.028rem;
  }

  &__new-posts-date {
    font-weight: 500;
    font-size: 1.6rem;
    line-height: 2.2rem;
    color: #787878;

    & span {
      color: #000;
    }
  }


}
</style>
