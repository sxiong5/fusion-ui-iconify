
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'JavascriptRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M15.54,10.5c0.1,0.29,0.38,0.5,0.71,0.5c0.41,0,0.75-0.34,0.75-0.75V10c0-0.55-0.45-1-1-1h-3c-0.55,0-1,0.45-1,1v1.5 c0,0.55,0.45,1,1,1h2.5v1h-2.04v0c-0.1-0.29-0.38-0.5-0.71-0.5C12.34,13,12,13.34,12,13.75V14c0,0.55,0.45,1,1,1h3 c0.55,0,1-0.45,1-1v-1.5c0-0.55-0.45-1-1-1h-2.5v-1L15.54,10.5z M7.5,13.5H9V9.75C9,9.34,9.34,9,9.75,9c0.41,0,0.75,0.34,0.75,0.75 v3.75c0,0.83-0.67,1.5-1.5,1.5H7.5C6.67,15,6,14.33,6,13.5v-0.25c0-0.41,0.34-0.75,0.75-0.75c0.41,0,0.75,0.34,0.75,0.75V13.5z"/></g>
  </svg>
</template>
        