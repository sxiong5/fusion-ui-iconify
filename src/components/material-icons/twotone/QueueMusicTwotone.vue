
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'QueueMusicTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><circle cx="16" cy="17" enable-background="new" opacity=".3" r="1"/><path d="M3,10h12v2H3V10z M3,14h8v2H3V14z M3,6h12v2H3V6z M17,14.18C16.69,14.07,16.35,14,16,14c-1.66,0-3,1.34-3,3s1.34,3,3,3 s3-1.34,3-3V8h3V6h-5V14.18z"/></g>
  </svg>
</template>
        