
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SolarPowerSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon points="3.33,16 11,16 11,13 4,13"/><polygon points="13,16 20.67,16 20,13 13,13"/><polygon points="21.11,18 13,18 13,22 22,22"/><polygon points="2,22 11,22 11,18 2.89,18"/><rect height="3" width="2" x="11" y="8"/><rect height="3" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -0.2089 14.6085)" width="2" x="16.53" y="6.06"/><rect height="2" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -3.448 6.7885)" width="3" x="4.97" y="6.56"/><rect height="2" width="3" x="3" y="2"/><rect height="2" width="3" x="18" y="2"/><path d="M12,7c2.76,0,5-2.24,5-5H7C7,4.76,9.24,7,12,7z"/></g></g>
  </svg>
</template>
        