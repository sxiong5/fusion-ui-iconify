
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'GasMeterRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M16,4h-1V3c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v1h-2V3c0-0.55-0.45-1-1-1h0C9.45,2,9,2.45,9,3v1H8C5.79,4,4,5.79,4,8 v10c0,2.21,1.79,4,4,4h8c2.21,0,4-1.79,4-4V8C20,5.79,18.21,4,16,4z M12,18c-1.38,0-2.5-1.1-2.5-2.46c0-1.02,0.38-1.35,2.12-3.35 c0.2-0.23,0.56-0.23,0.75,0c1.73,1.99,2.12,2.34,2.12,3.35C14.5,16.9,13.38,18,12,18z M15,10H9c-0.55,0-1-0.45-1-1v0 c0-0.55,0.45-1,1-1h6c0.55,0,1,0.45,1,1v0C16,9.55,15.55,10,15,10z"/></g>
  </svg>
</template>
        