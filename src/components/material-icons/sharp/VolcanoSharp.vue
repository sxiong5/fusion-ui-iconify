
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VolcanoSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><polygon points="18,8 11,8 9,13 6,13 2,22 22,22"/></g><g><rect height="4" width="2" x="13" y="1"/></g><g><rect height="2" transform="matrix(0.7071 -0.7071 0.7071 0.7071 1.9792 14.2929)" width="4" x="16.24" y="3.76"/></g><g><rect height="4" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -0.5061 8.2929)" width="2" x="8.76" y="2.76"/></g></g></g>
  </svg>
</template>
        