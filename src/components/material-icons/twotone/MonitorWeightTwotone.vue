
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MonitorWeightTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><rect height="1" opacity=".3" width="1" x="13" y="8.5"/><rect height="1" opacity=".3" width="1" x="10" y="8.5"/><rect height="1" opacity=".3" width="1" x="11.5" y="8.5"/><path d="M5,19h14V5H5V19z M12,6c1.66,0,3,1.34,3,3s-1.34,3-3,3s-3-1.34-3-3S10.34,6,12,6z" opacity=".3"/><path d="M12,12c1.66,0,3-1.34,3-3s-1.34-3-3-3S9,7.34,9,9S10.34,12,12,12z M13,8.5h1v1h-1V8.5z M11.5,8.5h1v1h-1V8.5z M10,8.5h1v1 h-1V8.5z"/><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M19,19H5V5h14V19z"/></g></g>
  </svg>
</template>
        