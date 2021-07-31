<template>
  <main :style="{ backgroundColor: activeColor }">
    <div class="counter">Count: {{ count }}</div>
  </main>
  <Footer :colors="colors" :next="next" :selectedIndex="selectedIndex" />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Footer from "./components/Footer.vue";

export default defineComponent({
  name: "App",
  components: {
    Footer,
  },
  data() {
    return {
      count: 0,
      colors: [
        "#ECA400",
        "#01295F",
        "#228CDB",
        "#420C14",
        "#DA627D",
        "#2A7F62",
      ],
    };
  },
  methods: {
    next() {
      this.count++;
    },
  },
  computed: {
    selectedIndex(): number {
      return this.count % this.colors.length;
    },
    activeColor(): string {
      return this.colors[this.selectedIndex];
    },
  },
});
</script>

<style scoped>
main {
  width: 100%;
  height: 100%;
}
.counter {
  position: fixed;
  top: 1rem;
  right: 1rem;

  color: #090909;
  background-color: #fafafa;
  padding: 1rem 2rem;
  border-radius: 0.45rem;
  font-weight: bold;

  box-shadow: 0 0 2px 2px rgba(153, 153, 153, 0.5);
}
</style>
