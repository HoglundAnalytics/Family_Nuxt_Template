<template>
  <section class="parent">
          <div class="outer_wrapper">
            <h1></h1>
            <DynamicButton></DynamicButton>
            <div class="dot_holder">
             <IconDot></IconDot>
            </div>
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
section {
  margin-top: -$l_gap;
  background: green;
  width: 100%;
  height: 65vh;
}
</style>
