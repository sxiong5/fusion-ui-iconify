
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ThumbDownOffAltOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M15,3H6C5.17,3,4.46,3.5,4.16,4.22l-3.02,7.05C1.05,11.5,1,11.74,1,12v2c0,1.1,0.9,2,2,2h6.31l-0.95,4.57l-0.03,0.32 c0,0.41,0.17,0.79,0.44,1.06L9.83,23l6.59-6.59C16.78,16.05,17,15.55,17,15V5C17,3.9,16.1,3,15,3z M15,15l-4.34,4.34L12,14H3v-2 l3-7h9V15z M19,3h4v12h-4V3z"/></g></g>
  </svg>
</template>
        