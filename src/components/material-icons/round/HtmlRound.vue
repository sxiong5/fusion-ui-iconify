
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HtmlRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M21,15c-0.55,0-1-0.45-1-1V9.75C20,9.34,20.34,9,20.75,9s0.75,0.34,0.75,0.75v3.75h1.75c0.41,0,0.75,0.34,0.75,0.75 c0,0.41-0.34,0.75-0.75,0.75H21z M16,10.49h1v3.76c0,0.41,0.34,0.75,0.75,0.75s0.75-0.34,0.75-0.75V10c0-0.55-0.45-1-1-1H13 c-0.55,0-1,0.45-1,1v4.25c0,0.41,0.34,0.75,0.75,0.75s0.75-0.34,0.75-0.75V10.5h1v2.75c0,0.41,0.34,0.75,0.75,0.75 S16,13.66,16,13.25V10.49z M5,9.75C5,9.34,4.66,9,4.25,9S3.5,9.34,3.5,9.75V11h-2V9.75C1.5,9.34,1.16,9,0.75,9S0,9.34,0,9.75v4.5 C0,14.66,0.34,15,0.75,15s0.75-0.34,0.75-0.75V12.5h2v1.75C3.5,14.66,3.84,15,4.25,15S5,14.66,5,14.25V9.75z M10.25,10.5 c0.41,0,0.75-0.34,0.75-0.75C11,9.34,10.66,9,10.25,9h-3.5C6.34,9,6,9.34,6,9.75c0,0.41,0.34,0.75,0.75,0.75h1v3.75 C7.75,14.66,8.09,15,8.5,15s0.75-0.34,0.75-0.75V10.5H10.25z"/></g>
  </svg>
</template>
        