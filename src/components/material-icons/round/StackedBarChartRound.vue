
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'StackedBarChartRound',
  props: svgIconProps,
  setup(props) {
    const fontSize = computed(() => {
      const _size = +props.size;
      if (isNaN(_size)) {
        const [_, size, unit] = /(d+)(w+)/.exec(props.size as string) || [];
        return unit === 'px' ? pxToRem(+size) : props.size;
      } else {
        return pxToRem(_size);
      }
    });

    return {
      fontSize,
      color: props.color
    };
  }
}
</script>

<template>
  <svg class="fn-icon-material fn-icon"
    :style="{ '--fn-icon-font-size': fontSize, '--fn-icon-color': $props.color }"
     xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="24" viewBox="0 0 24 24" width="24"
  >
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M6,20L6,20c1.1,0,2-0.9,2-2V9H4v9C4,19.1,4.9,20,6,20z"/><path d="M4,8h4V6c0-1.1-0.9-2-2-2h0C4.9,4,4,4.9,4,6V8z"/><path d="M10,11h4V9c0-1.1-0.9-2-2-2h0c-1.1,0-2,0.9-2,2V11z"/><path d="M16,12v2h4v-2c0-1.1-0.9-2-2-2h0C16.9,10,16,10.9,16,12z"/><path d="M18,20L18,20c1.1,0,2-0.9,2-2v-3h-4v3C16,19.1,16.9,20,18,20z"/><path d="M12,20L12,20c1.1,0,2-0.9,2-2v-6h-4v6C10,19.1,10.9,20,12,20z"/></g></g>
  </svg>
</template>
        