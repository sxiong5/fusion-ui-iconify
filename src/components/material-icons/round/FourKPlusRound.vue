
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FourKPlusRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M10.25,13.5H10v0.75 C10,14.66,9.66,15,9.25,15h0c-0.41,0-0.75-0.34-0.75-0.75V13.5h-2c-0.55,0-1-0.45-1-1V9.75C5.5,9.34,5.84,9,6.25,9h0 C6.66,9,7,9.34,7,9.75V12h1.5V9.75C8.5,9.34,8.84,9,9.25,9h0C9.66,9,10,9.34,10,9.75V12h0.25c0.41,0,0.75,0.34,0.75,0.75v0 C11,13.16,10.66,13.5,10.25,13.5z M15.09,15L15.09,15c-0.22,0-0.42-0.1-0.55-0.27L13,12.75v1.55c0,0.39-0.31,0.7-0.7,0.7H12.2 c-0.39,0-0.7-0.31-0.7-0.7V9.7c0-0.39,0.31-0.7,0.7-0.7h0.09C12.69,9,13,9.31,13,9.7v1.55l1.54-1.98C14.67,9.1,14.88,9,15.09,9h0 c0.58,0,0.91,0.66,0.56,1.12L14.25,12l1.41,1.88C16,14.34,15.67,15,15.09,15z M18.5,12.5h-1v1c0,0.28-0.22,0.5-0.5,0.5l0,0 c-0.28,0-0.5-0.22-0.5-0.5v-1h-1c-0.28,0-0.5-0.22-0.5-0.5v0c0-0.28,0.22-0.5,0.5-0.5h1v-1c0-0.28,0.22-0.5,0.5-0.5l0,0 c0.28,0,0.5,0.22,0.5,0.5v1h1c0.28,0,0.5,0.22,0.5,0.5v0C19,12.28,18.78,12.5,18.5,12.5z"/></g>
  </svg>
</template>
        