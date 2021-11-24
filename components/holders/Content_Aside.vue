<template>
  <section>
    <div class="bar">
      <div class="text_holder">
        <h1 class="t1">test</h1>
      </div>
    </div>
    <div class="circle"></div>
  </section>
</template>

<script></script>

<style lang="scss" scoped>
section {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  background: linear-gradient(to right, blue 80%, white 83%);
  .bar {
    grid-column: span 2;
    display: grid;
    .text_holder {
      place-self: center;
      width: 80%;
    }
  }
  .circle {
    background: red;
    border-radius: 360px;
    aspect-ratio: 1/1;
  }
}
</style>
