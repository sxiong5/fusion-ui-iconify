
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BedroomParentOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M18.35,11.45V9c0-1.1-0.9-2-2-2H13c-0.37,0-0.72,0.12-1,0.32C11.72,7.12,11.37,7,11,7H7.65c-1.1,0-2,0.9-2,2v2.45 C5.25,11.91,5,12.51,5,13.17V17h1.5v-1.5h11V17H19v-3.83C19,12.51,18.75,11.91,18.35,11.45z M16.75,10.5h-4v-2h4V10.5z M7.25,8.5h4 v2h-4V8.5z M17.5,14h-11v-1c0-0.55,0.45-1,1-1h9c0.55,0,1,0.45,1,1V14z M20,4v16H4V4H20 M20,2H4C2.9,2,2,2.9,2,4v16 c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V4C22,2.9,21.1,2,20,2z"/></g>
  </svg>
</template>
        