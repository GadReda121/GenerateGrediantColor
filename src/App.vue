<template>
    <div class="parent">
      <Preloader />
      <div class="generate">
          <Generate />
      </div>
      <Rate />
    </div>
</template>

<script>
import Rate from "./components/Rate.vue";
import Generate from "./components/Generate.vue";
import Preloader from "./components/Preloader.vue";

export default {
  components: {
    Rate,
    Generate,
    Preloader
  }
}
</script>

<style scoped>
  .parent{
      display:grid;
      justify-content: center;
      max-width: 100%;
      height: 90vh;
      align-items: center;
  }
</style>