
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PinOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M20,4H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6C22,4.9,21.1,4,20,4z M20,18H4V6h16V18z"/><polygon points="6.49,10.5 6.49,15 7.64,15 7.64,9 6.77,9 5.01,10.27 5.59,11.16"/><path d="M11.47,10.05c0.5,0,0.81,0.32,0.81,0.72c0,0.37-0.14,0.64-0.54,1.06c-0.36,0.38-1.06,1.08-2.13,2.15V15h3.89v-0.99h-2.37 l-0.03-0.05c0.68-0.68,1.15-1.14,1.4-1.39c0.61-0.6,0.92-1.22,0.92-1.86c0-0.24-0.05-1.04-0.91-1.48C12.04,9,11.25,8.87,10.56,9.2 c-0.82,0.39-0.99,1.13-1,1.15l1.01,0.42C10.67,10.44,10.95,10.05,11.47,10.05z"/><path d="M16.99,13.94c-0.83,0-0.99-0.76-1.02-0.86l-1.03,0.41c0.45,1.59,2.01,1.51,2.05,1.51c1.2,0,1.68-0.72,1.76-0.85 c0.32-0.49,0.36-1.24-0.01-1.76c-0.17-0.24-0.4-0.41-0.68-0.52V11.8c0.2-0.1,0.37-0.26,0.52-0.48c0.26-0.41,0.31-1.07-0.02-1.57 C18.48,9.64,18.03,9,16.94,9c-1.26,0-1.74,0.9-1.85,1.24l0.99,0.41c0.11-0.32,0.35-0.64,0.85-0.64c0.44,0,0.75,0.26,0.75,0.65 c0,0.58-0.55,0.72-0.88,0.72h-0.46v1h0.5c0.56,0,1.04,0.24,1.04,0.79C17.88,13.66,17.4,13.94,16.99,13.94z"/></g></g>
  </svg>
</template>
        