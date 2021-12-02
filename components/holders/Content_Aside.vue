<template>
  <section :class="{left: flip, right: !flip}">
    <div class="bar">
      <div class="text_holder">
        <h1 class="t1">test</h1>
      </div>
    </div>
    <div class="circle">
<PhotoBall></PhotoBall>

    </div>
  </section>
</template>

<script>
import PhotoBall from "./Photo_Ball.vue";
export default {
    components: { PhotoBall },
    props: {
        flip: {
            default: false,
            type: Boolean,
        }
    },
} 


</script>

<style lang="scss" scoped>
section {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  .bar {
    grid-column: span 2;
    display: grid;
    height: 80%;
    grid-area: 1/1/1/4;
    align-self: center;
    .text_holder {
      place-self: center;
      width: 80%;
    }
  }
  .circle {
    border-radius: 360px;
    aspect-ratio: 1/1;
    display: grid;
  }
}
  .right {
  .bar {
    display: grid;
    background: linear-gradient(to right, blue 80%, white 83%);
  }
  .circle {
    aspect-ratio: 1/1;
    grid-area: 1/3
  }
  }
  .left {
  .bar {
    display: grid;
    text-align: right;
    background: linear-gradient(to left, blue 80%, white 83%);
  }
  .circle {
    aspect-ratio: 1/1;
    grid-area: 1/1;
  }
  }
</style>
