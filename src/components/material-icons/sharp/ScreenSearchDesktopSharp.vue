
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenSearchDesktopSharp',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><rect height="2" width="22" x="1" y="19"/><path d="M22,3H2v15h19.99L22,3z M15.47,15.03l-2.09-2.09c-1.35,0.87-3.17,0.71-4.36-0.47c-1.37-1.37-1.37-3.58,0-4.95 s3.58-1.37,4.95,0c1.18,1.18,1.34,3,0.47,4.36l2.09,2.09L15.47,15.03z"/><circle cx="11.5" cy="10" r="2"/></g></g>
  </svg>
</template>
        