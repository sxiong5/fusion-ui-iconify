
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ViewCarouselRound',
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
    <rect fill="none" height="24" width="24"/><path d="M3,7h2c0.55,0,1,0.45,1,1v8c0,0.55-0.45,1-1,1H3c-0.55,0-1-0.45-1-1V8C2,7.45,2.45,7,3,7z M8,19h8c0.55,0,1-0.45,1-1V6 c0-0.55-0.45-1-1-1H8C7.45,5,7,5.45,7,6v12C7,18.55,7.45,19,8,19z M19,7h2c0.55,0,1,0.45,1,1v8c0,0.55-0.45,1-1,1h-2 c-0.55,0-1-0.45-1-1V8C18,7.45,18.45,7,19,7z"/>
  </svg>
</template>
        