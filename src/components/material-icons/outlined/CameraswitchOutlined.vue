
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CameraswitchOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M16,7h-1l-1-1h-4L9,7H8C6.9,7,6,7.9,6,9v6c0,1.1,0.9,2,2,2h8c1.1,0,2-0.9,2-2V9C18,7.9,17.1,7,16,7z M16,15H8V9h1.83l1-1 h2.34l1,1H16V15z"/><circle cx="12" cy="12" r="2"/><path d="M8.57,0.52L13.05,5l1.41-1.41l-1.54-1.54C17.7,2.46,21.53,6.24,22,11h2C23.36,3.3,15.79-1.67,8.57,0.52z"/><path d="M9.54,20.41l1.54,1.54C6.3,21.54,2.47,17.76,2,13H0c0.64,7.7,8.21,12.67,15.43,10.48L10.95,19L9.54,20.41z"/></g></g>
  </svg>
</template>
        