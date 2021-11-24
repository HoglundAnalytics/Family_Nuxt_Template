<template>
  <section class="parent">
    <div class="wrapper">
      <div class="hero_left">
        <div class="hero_content">
          <h1></h1>
          <DynamicButton></DynamicButton>
          <div class="dot_holder">
            <IconDot></IconDot>
          </div>
        </div>
      </div>
      <div class="hero_right"></div>
    </div>
  </section>
</template>

<script>
import DynamicButton from './holders/Dynamic_Button.vue'
import IconDot from './Icon_Dot.vue'
export default {
  components: {
    DynamicButton,
    IconDot,
  },
  computed: {
    content() {
      return this.$store.state.content.hero
    },
    headlines() {
      return this.$store.state.headlines
    },
    hlSet() {
      return this.headlines.inUse
    },
  },
}
</script>
<style lang="scss" scoped>
@mixin hero_sides {
  min-height: 80vh;
  width: 50%;
  box-sizing: border-box;
  @media (max-width: $break) {
    width: 100%;
    min-height: 50vh;
  }
}
section {
  margin-top: -$l_gap;
  background: green;
  width: 100%;
  .wrapper {
    background: red;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    .hero_left {
      @include hero_sides;

      padding: 3rem 0 0 0;
      display: grid;
    }
    .hero_right {
      @include hero_sides;

      padding: 3rem 2rem 2rem 2rem;
      display: grid;
    }
  }
}
</style>
