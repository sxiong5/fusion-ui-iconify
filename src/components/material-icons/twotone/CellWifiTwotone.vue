
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CellWifiTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M6,22h16V5.97L6,22z M20,20h-2v-7.22l2-2V20z M5.22,7.22L3.93,5.93c3.9-3.91,10.24-3.91,14.15,0l-1.29,1.29 C13.6,4.03,8.41,4.03,5.22,7.22z M12.93,11.07L11,13l-1.93-1.93C10.14,10.01,11.86,10.01,12.93,11.07z M14.22,9.79 c-1.78-1.77-4.66-1.77-6.43,0L6.5,8.5c2.48-2.48,6.52-2.48,9,0L14.22,9.79z"/></g>
  </svg>
</template>
        