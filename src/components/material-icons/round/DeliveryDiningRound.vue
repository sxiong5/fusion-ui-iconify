
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DeliveryDiningRound',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><g><path d="M19,7c0-1.1-0.9-2-2-2h-2c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2v2.65L13.52,14H10v-4c0-0.55-0.45-1-1-1H6 c-2.21,0-4,1.79-4,4v2c0,0.55,0.45,1,1,1h1c0,1.66,1.34,3,3,3s3-1.34,3-3h3.52c0.61,0,1.18-0.28,1.56-0.75l3.48-4.35 C18.85,10.54,19,10.1,19,9.65V7z M7,17c-0.55,0-1-0.45-1-1h2C8,16.55,7.55,17,7,17z"/><path d="M6,6h3c0.55,0,1,0.45,1,1v0c0,0.55-0.45,1-1,1H6C5.45,8,5,7.55,5,7v0C5,6.45,5.45,6,6,6z"/><path d="M19,13c-1.66,0-3,1.34-3,3s1.34,3,3,3s3-1.34,3-3S20.66,13,19,13z M19,17c-0.55,0-1-0.45-1-1s0.45-1,1-1s1,0.45,1,1 C20,16.55,19.55,17,19,17z"/></g></g></g>
  </svg>
</template>
        