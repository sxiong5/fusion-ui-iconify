
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenSearchDesktopOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M4,18h16c1.1,0,1.99-0.9,1.99-2L22,5c0-1.1-0.9-2-2-2H4C2.9,3,2,3.9,2,5v11C2,17.1,2.9,18,4,18z M4,5h16v11H4V5z"/><rect height="2" width="22" x="1" y="19"/><path d="M13.97,7.53c-1.37-1.37-3.58-1.37-4.95,0s-1.37,3.58,0,4.95c1.18,1.18,3,1.34,4.36,0.47l2.09,2.09l1.06-1.06l-2.09-2.09 C15.31,10.53,15.16,8.71,13.97,7.53z M12.91,11.41c-0.78,0.78-2.05,0.78-2.83,0c-0.78-0.78-0.78-2.05,0-2.83s2.05-0.78,2.83,0 C13.69,9.37,13.69,10.63,12.91,11.41z"/></g></g>
  </svg>
</template>
        