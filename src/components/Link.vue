<template>
  <a :href="url" target="_blank" rel="noopener noreferrer">
    <img :src="imageSrc" :alt="altText" class="link-image" />
  </a>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Link',
  props: {
    url: {
      type: String,
      required: true
    },
    imageSrc: {
      type: String,
      required: true
    },
    altText: {
      type: String,
      default: 'Link image'
    }
  }
});
</script>

<style scoped>
.link-image {
  width: 40px;
  height: 40px;
  object-fit: contain;
  transition: opacity 0.3s ease;
}

</style>
