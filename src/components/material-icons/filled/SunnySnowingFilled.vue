
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SunnySnowingFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M13 5h-2V1h2v4zM1 11h4v2H1v-2zm18 2v-2h4v2h-4zm-1.34-5.24-1.41-1.41 2.83-2.83 1.41 1.41-2.83 2.83zM3.51 4.93l1.41-1.41 2.83 2.83-1.41 1.41-2.83-2.83zM4.75 17a1.25 1.25 0 102.5 0 1.25 1.25 0 00-2.5 0zm12 0a1.25 1.25 0 102.5 0 1.25 1.25 0 00-2.5 0zm-9 4a1.25 1.25 0 102.5 0 1.25 1.25 0 00-2.5 0zm3-4a1.25 1.25 0 102.5 0 1.25 1.25 0 00-2.5 0zm3 4a1.25 1.25 0 102.5 0 1.25 1.25 0 00-2.5 0zM17 13v-1c0-2.76-2.24-5-5-5s-5 2.24-5 5v1h10z"/></g>
  </svg>
</template>
        