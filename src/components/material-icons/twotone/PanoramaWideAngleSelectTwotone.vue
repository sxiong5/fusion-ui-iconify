
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PanoramaWideAngleSelectTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M12,4C8.03,4,5.15,4.63,3,5c-0.55,1.97-1,3.92-1,7c0,3.03,0.45,5.05,1,7c2.15,0.37,4.98,1,9,1c3.97,0,6.85-0.63,9-1 c0.57-2.02,1-3.99,1-7c0-3.03-0.45-5.05-1-7C18.85,4.63,16.02,4,12,4z"/></g></g></g>
  </svg>
</template>
        