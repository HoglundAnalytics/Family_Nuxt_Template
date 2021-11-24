<template>
  <section>
    <div id="overlap_wrapper">
      <div class="overlap"></div>
      <div class="content_wrapper">
        <FormComponent />
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
      background: tan;
      width: 100%;
      border-radius: 100% 100% 100% 100%;
      margin-bottom: -($overlap_height / 2);
    }
  }
  .content_wrapper {
    background: $main_color;
    height: 500px;
    display: grid;
    gap: $gap;
  }
}
</style>
