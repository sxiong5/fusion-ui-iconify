
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AlarmOffSharp',
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
     xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"
  >
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M10.04 6.29C10.66 6.11 11.32 6 12 6c3.86 0 7 3.14 7 7 0 .68-.11 1.34-.29 1.96l1.56 1.56c.47-1.08.73-2.27.73-3.52 0-4.97-4.03-9-9-9-1.25 0-2.44.26-3.53.72l1.57 1.57zm7.297-4.48l4.607 3.845-1.28 1.535-4.61-3.843zM3.02 2.1L1.61 3.51l1.37 1.37-.92.77 1.28 1.54 1.06-.88.8.8C3.83 8.69 3 10.75 3 13c0 4.97 4.03 9 9 9 2.25 0 4.31-.83 5.89-2.2l2.1 2.1 1.41-1.41L3.02 2.1zM12 20c-3.86 0-7-3.14-7-7 0-1.7.61-3.26 1.62-4.47l9.85 9.85C15.26 19.39 13.7 20 12 20zM7.48 3.73l.46-.38-1.28-1.54-.6.5z"/>
  </svg>
</template>
        