
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AirplaneTicketTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M4.01,8.54C5.2,9.23,6,10.52,6,12c0,1.47-0.81,2.77-2,3.46V18h16V6H4L4.01,8.54z M8.14,12.53l1.26,0.99 l2.39-0.64l-2.4-4.16l1.4-0.38l4.01,3.74l2.44-0.65c0.51-0.14,1.04,0.17,1.18,0.68c0.13,0.51-0.17,1.04-0.69,1.19l-8.86,2.36 l-1.66-2.88L8.14,12.53z" opacity=".3"/><path d="M20.19,4H4C2.9,4,2.01,4.9,2.01,6v4C3.11,10,4,10.9,4,12s-0.89,2-2,2v4c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6 C22,4.9,21.19,4,20.19,4z M20,18H4v-2.54c1.19-0.69,2-1.99,2-3.46c0-1.48-0.8-2.77-1.99-3.46L4,6h16V18z"/><path d="M17.73,13.3c0.52-0.15,0.82-0.68,0.69-1.19c-0.14-0.51-0.67-0.82-1.18-0.68l-2.44,0.65l-4.01-3.74l-1.4,0.38l2.4,4.16 L9.4,13.52l-1.26-0.99l-0.93,0.25l1.66,2.88L17.73,13.3z"/></g></g>
  </svg>
</template>
        