
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FlashlightOnTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M8,7.39l2,3V20h4v-9.6l2-3.01V7H8V7.39z M12,12.5c0.83,0,1.5,0.67,1.5,1.5s-0.67,1.5-1.5,1.5 s-1.5-0.67-1.5-1.5S11.17,12.5,12,12.5z" opacity=".3"/><rect height="1" opacity=".3" width="8" x="8" y="4"/><path d="M6,2v6l2,3v11h8V11l2-3V2H6z M16,7.39l-2,3.01V20h-4v-9.61l-2-3V7h8V7.39z M16,5H8V4h8V5z"/><circle cx="12" cy="14" r="1.5"/></g></g>
  </svg>
</template>
        