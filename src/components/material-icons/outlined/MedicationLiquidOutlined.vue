
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MedicationLiquidOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><rect height="2" width="12" x="3" y="3"/><path d="M2,21h14V6H2V21z M5,12h2.5V9.5h3V12H13v3h-2.5v2.5h-3V15H5V12z"/><path d="M20,6c-1.68,0-3,1.76-3,4c0,1.77,0.83,3.22,2,3.76V21h2v-7.24c1.17-0.54,2-1.99,2-3.76C23,7.76,21.68,6,20,6z"/></g></g>
  </svg>
</template>
        