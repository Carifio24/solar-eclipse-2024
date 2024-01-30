<template>
  <div class="colorbar">
  </div>
</template>

<script lang="ts">
import { PropType, defineComponent } from 'vue';

export default defineComponent({
  props: {
    colors: {
      type: Array as PropType<[number, string][]>,
      required: true
    }
  }
});
</script>

<style lang="less">
.colorbar {
}
</style>
