
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FilePresentTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M14,4H6v16h12V8h-4V4z M16,11v4c0,2.21-1.79,4-4,4s-4-1.79-4-4V9.5C8,8.12,9.12,7,10.5,7S13,8.12,13,9.5V15 h-2V9.5C11,9.22,10.78,9,10.5,9S10,9.22,10,9.5V15c0,1.1,0.9,2,2,2s2-0.9,2-2v-4H16z" opacity=".3"/><path d="M14,15c0,1.1-0.9,2-2,2s-2-0.9-2-2V9.5C10,9.22,10.22,9,10.5,9S11,9.22,11,9.5V15h2V9.5C13,8.12,11.88,7,10.5,7 S8,8.12,8,9.5V15c0,2.21,1.79,4,4,4s4-1.79,4-4v-4h-2V15z"/><path d="M14,2H6C4.9,2,4,2.9,4,4v16c0,1.1,0.9,2,2,2h12c1.1,0,2-0.9,2-2V8L14,2z M18,20H6V4h8v4h4V20z"/></g></g>
  </svg>
</template>
        