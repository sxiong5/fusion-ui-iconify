
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WaterfallChartRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M19.5,4L19.5,4C20.33,4,21,4.67,21,5.5v13c0,0.83-0.67,1.5-1.5,1.5h0c-0.83,0-1.5-0.67-1.5-1.5v-13 C18,4.67,18.67,4,19.5,4z M4.5,13L4.5,13C5.33,13,6,13.67,6,14.5v4C6,19.33,5.33,20,4.5,20h0C3.67,20,3,19.33,3,18.5v-4 C3,13.67,3.67,13,4.5,13z M15.5,4L15.5,4C16.33,4,17,4.67,17,5.5v0C17,6.33,16.33,7,15.5,7h0C14.67,7,14,6.33,14,5.5v0 C14,4.67,14.67,4,15.5,4z M11.5,5L11.5,5C12.33,5,13,5.67,13,6.5v1C13,8.33,12.33,9,11.5,9h0C10.67,9,10,8.33,10,7.5v-1 C10,5.67,10.67,5,11.5,5z M8.5,10L8.5,10c0.83,0,1.5,0.67,1.5,1.5v1c0,0.83-0.67,1.5-1.5,1.5h0C7.67,14,7,13.33,7,12.5v-1 C7,10.67,7.67,10,8.5,10z"/></g></g>
  </svg>
</template>
        