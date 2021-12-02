<template>
  <section>
    <div id="overlap_wrapper">
      <div class="overlap"></div>
      <div class="content_wrapper">
        <div class="outer_wrapper">
        <FormComponent />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import FormComponent from './Form_Component.vue'

export default {
  components: {
    FormComponent,
  },
}
</script>

<style lang="scss" scoped>
$overlap_height: 25rem;
section {
  margin-top: -(($overlap_height/2) + $l_gap);
  #overlap_wrapper {
    .overlap {
      height: $overlap_height;
      background: url(~/assets/img/backgrounds/form_bubble.svg) no-repeat;
      background-size: cover;
      background-position-y: 40px;
      width: 100%;
      border-radius: 100% 100% 100% 100%;
      margin-bottom: -($overlap_height / 2);
    }
  }
  .content_wrapper {
    background: url(~/assets/img/backgrounds/background_dots-01.svg),$main_color;
    height: 500px;
    display: grid;
    gap: $gap;
  }
}
</style>
