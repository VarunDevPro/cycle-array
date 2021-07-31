<template>
  <footer>
    <ColorDot
      v-for="(item, index) in colors"
      :key="item"
      :color="item"
      :index="index"
      :selected="index === selectedIndex"
    />
    <div class="wrapper">
      <button class="next" @click="next">Next</button>
    </div>
  </footer>
</template>

<script lang="ts">
import { PropType, defineComponent } from "vue";
import ColorDot from "./ColorDot.vue";

export default defineComponent({
  name: "Footer",
  components: {
    ColorDot,
  },
  props: {
    colors: {
      type: Array as PropType<string[]>,
      required: true,
    },
    next: {
      type: Function as any,
      required: true,
    },
    selectedIndex: {
      type: Number,
      required: true,
    },
  },
});
</script>

<style scoped>
footer {
  padding: 3rem 0 4rem;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: rgba(255, 255, 255, 0.7);
  border-top: 2px solid rgb(225, 225, 225, 0.9);
}

div.wrapper {
  margin-top: 2rem;
}
button.next {
  background-color: #090909;
  color: #fafafa;
  padding: 1rem 2rem;
  border-radius: 0.45rem;
  font-weight: bold;
  cursor: pointer;
}
button.next:hover {
  background-color: #222222;
}
</style>
