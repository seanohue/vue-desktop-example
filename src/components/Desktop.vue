<script>
import draggable from 'vuedraggable'

import DesktopIcon from './DesktopIcon.vue'

export default {
  name: "desktop",
  components: {
    DesktopIcon,
    draggable
  },
  data() {
    return {
      icons: [
        { label: "OBS Studio", id: 0 },
        { label: "Godot Engine", id: 1 },
        { label: "Firefox", id: 2 },
        { label: "Chrome", id: 3 },
        { label: "Steam", id: 4},
        { label: "Slack", id: 5 },
        { label: "Discord", id: 6 },
        { label: "Ableton Live", id: 7 },
      ],
    }
  },
}

</script>

<template>
  <div class="desktop">
    <draggable
      v-model="icons"
      class="draggable-container"
      :delay="500"
      item-key="id">
      <template #item="{ element: icon }">
        <DesktopIcon :icon="icon" />
      </template>
    </draggable>
  </div>
</template>

<style scoped>
.desktop {
  width: 100vw;
  text-align: center;
}

.draggable-container {
  display: flex;
  flex-flow: row wrap;
  min-width: 500px;
}

</style>