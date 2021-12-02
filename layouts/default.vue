<template>
  <div id="main_wrapper">
    <nuxt />
    <Header :scroll-location="scroll_location" />
    <Hero />
    <HeroOverlap />
    <Floater :scroll-location="scroll_location"
      ><TT_OT>
        <div>
          <h1 class="t3">{{ noWidow(content.largestBlock.headline) }}</h1>
          <h2 class="t5 accent_text">
            {{ noWidow(content.largestBlock.subhead) }}
          </h2>
        </div>
        <img />
      </TT_OT>
    </Floater>
    <Badges v-if="content.badges" :scroll-location="scroll_location" />
    <ContentAside />
    <ContentAside :flip="true" />
    <Cta :scroll-location="scroll_location" :content="content.cta1"> </Cta>
    <FooterComponent>
      <Reviews />
      <Cta :scroll-location="scroll_location" :content="content.cta2"> </Cta>
      <Disclaimer />
      <Copyright />
    </FooterComponent>
  </div>
</template>

<script>
import Header from '../components/Header_Component.vue'
import Hero from '../components/Hero.vue'
import HeroOverlap from '../components/Hero_Overlap.vue'
import Floater from '../components/holders/Floater.vue'
import Badges from '../components/Badges.vue'
import Cta from '../components/Cta.vue'
import TT_OT from '../components/holders/TT_OT.vue'
import FooterComponent from '../components/holders/Footer_component.vue'
import Reviews from '../components/Reviews.vue'
import Disclaimer from '../components/Disclaimer.vue'
import Copyright from '../components/Copyright.vue'
import ContentAside from '../components/holders/Content_Aside.vue'

export default {
  components: {
    Header,
    Hero,
    HeroOverlap,
    Floater,
    Badges,
    Cta,
    TT_OT,
    FooterComponent,
    Reviews,
    Disclaimer,
    Copyright,
    ContentAside,
  },
  data() {
    return {
      test: 1,
      scroll_location: 0,
    }
  },
  computed: {
    content() {
      return this.$store.state.content
    },
  },
  mounted() {
    window.addEventListener(
      'scroll',
      this.debounce(() => this.setData())
    )
  },
  destroyed() {
    window.removeEventListener(
      'scroll',
      this.debounce(() => this.setData())
    )
  },
  methods: {
    debounce(func, timeout = 10) {
      // todo add timeout logic
      return (...args) => {
        func.apply(this.args)
      }
    },
    setData() {
      this.scroll_location = window.pageYOffset
    },

    scrollTo(location) {
      const loc = document.querySelector(`#${location}`)
      loc.scrollIntoView(true, { behavior: 'smooth' })
    },
  },
}
</script>

<style lang="scss" scoped>
#main_wrapper {
  display: grid;
  row-gap: $l_gap;
  #post_hero_button_row {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  #help {
    text-align: center;
  }
}
</style>
