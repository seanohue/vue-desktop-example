<script setup>
import cloudIcon from '/src/assets/img/cloud.png'

const props = defineProps({
  icon: {
    label: String,
  }
});
</script>

<template>
  <div class="desktop-icon-container">
    <div class="desktop-icon" :style="{ backgroundImage: `url(${cloudIcon})` }"></div>
    <span class="desktop-icon-label">{{ props.icon.label }}</span>
  </div>
</template>

<style scoped>
.desktop-icon-container {
  width: calc(1000px / 6);
  min-width: 40%;
  height: 192px;
}

@media only screen and (min-width: 500px) and (max-width: 999px) {
  .desktop-icon-container {
    min-width: 33%;
  }
}

@media only screen and (min-width: 1000px) {
  .desktop-icon-container {
    min-width: calc(100% / 6);
  }
}


.desktop-icon {
  height: 80px;
  width: 80px;
  margin: 0 auto 6px auto;
  background-size: contain;
}

.desktop-icon-label {
  text-shadow: 1px 1px rgb(0 0 0 / 0.2);
}

</style>