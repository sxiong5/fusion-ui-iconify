
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ViewModuleRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M14.67,6v4.5c0,0.55-0.45,1-1,1h-3.33c-0.55,0-1-0.45-1-1V6c0-0.55,0.45-1,1-1h3.33C14.22,5,14.67,5.45,14.67,6z M16.67,11.5H20c0.55,0,1-0.45,1-1V6c0-0.55-0.45-1-1-1h-3.33c-0.55,0-1,0.45-1,1v4.5C15.67,11.05,16.11,11.5,16.67,11.5z M14.67,18v-4.5c0-0.55-0.45-1-1-1h-3.33c-0.55,0-1,0.45-1,1V18c0,0.55,0.45,1,1,1h3.33C14.22,19,14.67,18.55,14.67,18z M15.67,13.5V18c0,0.55,0.45,1,1,1H20c0.55,0,1-0.45,1-1v-4.5c0-0.55-0.45-1-1-1h-3.33C16.11,12.5,15.67,12.95,15.67,13.5z M7.33,12.5H4c-0.55,0-1,0.45-1,1V18c0,0.55,0.45,1,1,1h3.33c0.55,0,1-0.45,1-1v-4.5C8.33,12.95,7.89,12.5,7.33,12.5z M8.33,10.5V6 c0-0.55-0.45-1-1-1H4C3.45,5,3,5.45,3,6v4.5c0,0.55,0.45,1,1,1h3.33C7.89,11.5,8.33,11.05,8.33,10.5z"/></g>
  </svg>
</template>
        