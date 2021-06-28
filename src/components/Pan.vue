<template>
  <div class="">
    <div>
      <div class="font-medium text-black">FEN</div>
      <p class="text-gray-500">{{ fen }}</p>
    </div>
    <div class="flex-shrink-0">
      <button class="mx-1" type="button" @click="count++">＋</button>
      {{ count }}
      <button class="mx-1" type="button" @click="count--">－</button>
    </div>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from "vue";
export default defineComponent({
  name: "Pan",
  props: {
    fen: {
      type: String,
      required: true,
    },
  },
  setup: () => {
    const count = ref(0);
    return { count };
  },
});
</script>
