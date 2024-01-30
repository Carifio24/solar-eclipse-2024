<template>
  <div
    class="colorbar"
    :style="{ background: gradient, width, height }"
  >
  </div>
</template>

<script lang="ts">
import { PropType, defineComponent } from 'vue';

export default defineComponent({
  props: {
    colors: {
      type: Array as PropType<[string, number][]>,
      required: true
    },
    orientation: {
      type: String as PropType<'horizontal' | 'vertical'>,
      default: 'vertical'
    },
    height: {
      type: String,
      default: "200px"
    },
    width: {
      type: String,
      default: "50px"
    }
  },

  computed: {
    gradient() {
      const angle = this.orientation === 'horizontal' ? 90 : 0;
      const colorStrings = this.colors.map(([color, value]) => `${color} ${value * 100}%`);
      const colorString = colorStrings.join(",\n");
      const s = `
        linear-gradient(
          ${angle}deg,
          ${colorString}
        )
      `;
      console.log(s);
      return s;
    }
  }
});
</script>

