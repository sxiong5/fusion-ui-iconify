
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CameraIndoorTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M6,10v9h12v-9l-6-4.5L6,10z M14,12v1l2-1.06v4.12L14,15v1c0,0.55-0.45,1-1,1H9c-0.55,0-1-0.45-1-1v-4 c0-0.55,0.45-1,1-1h4C13.55,11,14,11.45,14,12z" opacity=".3"/><path d="M8,12v4c0,0.55,0.45,1,1,1h4c0.55,0,1-0.45,1-1v-1l2,1.06v-4.12L14,13v-1c0-0.55-0.45-1-1-1H9C8.45,11,8,11.45,8,12z"/><path d="M12,3L4,9v12h16V9L12,3z M18,19H6v-9l6-4.5l6,4.5V19z"/></g></g>
  </svg>
</template>
        