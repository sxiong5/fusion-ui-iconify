
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ChargingStationTwotone',
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
    <g><rect fill="none" height="24" width="24"/><path d="M17,3v1H7V3H17 M17,20H7v1h10V20" opacity=".3"/><path d="M14.5,11l-3,6v-4h-2l3-6v4H14.5z M17,3H7v1h10V3 M17,20H7v1h10V20 M17,1c1.1,0,2,0.9,2,2v18c0,1.1-0.9,2-2,2H7 c-1.1,0-2-0.9-2-2V3c0-1.1,0.9-2,2-2H17L17,1z M7,18h10V6H7V18L7,18z"/></g>
  </svg>
</template>
        