
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SendAndArchiveOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M11,12l-6-1.5V7.01l8.87,3.73c0.94-0.47,2-0.75,3.13-0.75c0.1,0,0.19,0.01,0.28,0.01L3,4v16l7-2.95c0-0.02,0-0.03,0-0.05 c0-0.8,0.14-1.56,0.39-2.28L5,16.99V13.5L11,12z"/></g><g><path d="M17,12c-2.76,0-5,2.24-5,5s2.24,5,5,5s5-2.24,5-5S19.76,12,17,12z M17,20l-3-3l0.71-0.71l1.79,1.79V14h1v4.09l1.79-1.79 L20,17L17,20z"/></g></g></g>
  </svg>
</template>
        