<template>
  <div class="image-display">
    <img :src="imageSrc" :alt="alt">
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      default: 'Image'
    }
  },
  computed: {
    imageSrc() {
      return new URL(`/src/assets/Images/${this.src}`, import.meta.url).href;
    }
  },
  mounted() {
  console.log('Image URL:', this.imageSrc);
}
});
</script>

<style scoped>
.image-display {
  max-width: 100%;
  height: auto;
}

.image-display img {
  width: 100%;
  height: auto;
  object-fit: contain;
}
</style>