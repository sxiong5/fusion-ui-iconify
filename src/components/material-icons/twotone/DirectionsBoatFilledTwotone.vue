
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DirectionsBoatFilledTwotone',
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
    <rect fill="none" height="24" width="24"/><path d="M19.77,12.66l-1.12,3.97c-0.78-0.43-1.07-0.86-2.65-2.67C14.4,15.78,13.57,17,12,17c-1.53,0-2.34-1.15-4-3.04 c-1.6,1.82-1.87,2.21-2.65,2.65l-1.13-3.96L12,10.11L19.77,12.66z" opacity=".3"/><path d="M19.77,12.66l-1.12,3.97c-0.78-0.43-1.07-0.86-2.65-2.67C14.4,15.78,13.57,17,12,17c-1.53,0-2.34-1.15-4-3.04 c-1.6,1.82-1.87,2.21-2.65,2.65l-1.13-3.96L12,10.11L19.77,12.66z M15,1H9v3H6C4.9,4,4,4.9,4,6v4.62l-1.29,0.42 c-0.63,0.19-0.81,0.84-0.66,1.28L3.95,19H4c1.6,0,3.02-0.88,4-2c0.98,1.12,2.4,2,4,2s3.02-0.88,4-2c0.98,1.12,2.4,2,4,2h0.05 l1.91-6.68c0.11-0.37,0.04-1.06-0.66-1.28L20,10.62V6c0-1.1-0.9-2-2-2h-3V1L15,1z M6,9.97V6h12v3.97L12,8L6,9.97L6,9.97z M16,19.68 c-1.22,0.85-2.61,1.28-4,1.28s-2.78-0.43-4-1.28C6.78,20.53,5.39,21,4,21H2v2h2c1.38,0,2.74-0.35,4-0.99c1.26,0.64,2.63,0.97,4,0.97 s2.74-0.32,4-0.97c1.26,0.65,2.62,0.99,4,0.99h2v-2h-2C18.61,21,17.22,20.53,16,19.68L16,19.68z"/>
  </svg>
</template>
        