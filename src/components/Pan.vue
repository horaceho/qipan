<template>
  <div class="mx-auto px-4">
    <div class="text-center space-y-6 mb-6">
      <div class="text-lg leading-6 font-medium text-gray-900">FEN {{ xiang.version() }}</div>
      <p class="mt-2 text-xs text-gray-500">{{ fen }}</p>
    </div>

    <div class="max-w-sm mx-auto grid grid-cols-9 gap-4">
      <div v-for="(grid) in xiang.grids()" :key="grid.index">
        <div class="text-3xl">{{ grid.chi }}</div>
      </div>
    </div>

    <div class="text-center text-lg mt-6">
        <button class="mx-1" type="button" @click="count--">－</button>
        {{ count }}
        <button class="mx-1" type="button" @click="count++">＋</button>
    </div>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from "vue";
import { Xiang } from "xiang.js";

export default defineComponent({
  name: "Pan",
  props: {
    fen: {
      type: String,
      required: true,
    },
  },
  mounted() {
    this.xiang.start();
  },
  setup: () => {
    const count = ref(0);
    const xiang = new Xiang();
    return { count, xiang };
  },
});
</script>
