
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HlsRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M10.75,9C10.34,9,10,9.34,10,9.75V14c0,0.55,0.45,1,1,1h2.25c0.41,0,0.75-0.34,0.75-0.75s-0.34-0.75-0.75-0.75H11.5V9.75 C11.5,9.34,11.16,9,10.75,9z M19.04,10.5c0.1,0.29,0.38,0.5,0.71,0.5c0.41,0,0.75-0.34,0.75-0.75V10c0-0.55-0.45-1-1-1h-3 c-0.55,0-1,0.45-1,1v1.5c0,0.55,0.45,1,1,1H19v1h-2.04v0c-0.1-0.29-0.38-0.5-0.71-0.5c-0.41,0-0.75,0.34-0.75,0.75V14 c0,0.55,0.45,1,1,1h3c0.55,0,1-0.45,1-1v-1.5c0-0.55-0.45-1-1-1H17v-1L19.04,10.5z M8,9.75C8,9.34,7.66,9,7.25,9S6.5,9.34,6.5,9.75 V11h-2V9.75C4.5,9.34,4.16,9,3.75,9S3,9.34,3,9.75v4.5C3,14.66,3.34,15,3.75,15s0.75-0.34,0.75-0.75V12.5h2v1.75 C6.5,14.66,6.84,15,7.25,15S8,14.66,8,14.25V9.75z"/></g>
  </svg>
</template>
        