
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VideogameAssetOffOutlined',
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
    <rect fill="none" height="24" width="24" y="0"/><path d="M17.5,9c0.83,0,1.5,0.67,1.5,1.5S18.33,12,17.5,12S16,11.33,16,10.5S16.67,9,17.5,9z M10.83,8H20v8h-1.17l1.87,1.87 C21.45,17.58,22,16.85,22,16V8c0-1.1-0.9-2-2-2H8.83L10.83,8z M19.78,22.61L15.17,18H4c-1.1,0-2-0.9-2-2V8 c0-0.85,0.55-1.58,1.3-1.87L1.39,4.22l1.41-1.41l18.38,18.38L19.78,22.61z M13.17,16l-3-3H9v2H7v-2H5v-2h2V9.83L5.17,8H4v8H13.17z"/>
  </svg>
</template>
        