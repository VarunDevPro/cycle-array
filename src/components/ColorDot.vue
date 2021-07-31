<template>
  <div :class="{ selected: selected }" :style="{ backgroundColor: color }">
    <span class="sr-only">Choose color 1</span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ColorDot",
  props: {
    selected: {
      type: Boolean,
    },
    color: {
      type: String,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
});
</script>

<style scoped>
div {
  display: inline-block;
  border-radius: 50%;
  height: 2rem;
  width: 2rem;
  border: 2px solid transparent;
}

div.selected {
  box-shadow: 0 0 0 1px rgb(50, 50, 50), 0 0 0 3px rgb(255, 255, 255),
    0 0 5px 5px rgb(224, 230, 236);
}

div:not(:last-child) {
  margin-right: 1rem;
}
</style>
