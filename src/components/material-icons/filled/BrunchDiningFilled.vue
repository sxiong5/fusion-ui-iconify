
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BrunchDiningFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M18,8h2V4h-2V8z M15.51,22H2.49C2.22,22,2,21.78,2,21.5V20h14v1.5 C16,21.78,15.78,22,15.51,22z M18,15.89l-0.4-0.42c-1.02-1.08-1.6-2.52-1.6-4V2h6v9.51c0,1.46-0.54,2.87-1.53,3.94L20,15.97V20h2v2 h-4V15.89z M7,16v-2h4v2h4.5c0.28,0,0.5,0.22,0.5,0.5v1c0,0.28-0.22,0.5-0.5,0.5h-13C2.22,18,2,17.78,2,17.5v-1 C2,16.22,2.22,16,2.5,16H7z" fill-rule="evenodd"/></g>
  </svg>
</template>
        