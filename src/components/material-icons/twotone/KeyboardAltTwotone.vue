
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'KeyboardAltTwotone',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><path d="M3,19h18V6H3V19z M17,8h2v2h-2V8z M17,12h2v2h-2V12z M13,8h2v2h-2V8z M13,12h2 v2h-2V12z M9,8h2v2H9V8z M9,12h2v2H9V12z M8,16h8v1H8V16z M5,8h2v2H5V8z M5,12h2v2H5V12z" enable-background="new" opacity=".3"/><path d="M21,4H3C1.9,4,1,4.9,1,6v13c0,1.1,0.9,2,2,2h18c1.1,0,2-0.9,2-2V6C23,4.9,22.1,4,21,4z M21,19H3V6h18V19z"/><rect height="2" width="2" x="9" y="8"/><rect height="2" width="2" x="5" y="8"/><rect height="1" width="8" x="8" y="16"/><rect height="2" width="2" x="13" y="8"/><rect height="2" width="2" x="9" y="12"/><rect height="2" width="2" x="5" y="12"/><rect height="2" width="2" x="13" y="12"/><rect height="2" width="2" x="17" y="8"/><rect height="2" width="2" x="17" y="12"/></g></g>
  </svg>
</template>
        