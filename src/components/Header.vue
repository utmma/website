<template>
  <header class="header">
    <nav class="header__nav">
      <ul class="header__nav-list">
        <li class="header__nav-item"><a href="#" class="header__nav-link">Home</a></li>
        <li class="header__nav-item"><a href="#" class="header__nav-link">About Us</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Header',
});
</script>

<style scoped>
.header {
  background-color: #000;
}
.header__title {
  font-size: 1.5rem;
  color: #333;
  margin: 0;
}

.header__nav-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: grid;
  grid-template-columns: repeat(2, 80px);
  gap: 10px;
  justify-items: center;

}

.header__nav-item {
  box-sizing: border-box;

}
    
.header__nav-link {
  text-decoration: none;
  color: #ffffff;
  font-weight: 500;
  transition: color 0.3s ease;
}

.header__nav-link:hover {
  color: #007bff;
}
</style>
