
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AlignVerticalBottomRound',
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
    <rect fill="none" height="24" width="24"/><path d="M21,22H3c-0.55,0-1-0.45-1-1v0c0-0.55,0.45-1,1-1h18c0.55,0,1,0.45,1,1v0C22,21.55,21.55,22,21,22z M8.5,2L8.5,2 C7.67,2,7,2.67,7,3.5v13C7,17.33,7.67,18,8.5,18h0c0.83,0,1.5-0.67,1.5-1.5v-13C10,2.67,9.33,2,8.5,2z M15.5,8L15.5,8 C14.67,8,14,8.67,14,9.5v7c0,0.83,0.67,1.5,1.5,1.5h0c0.83,0,1.5-0.67,1.5-1.5v-7C17,8.67,16.33,8,15.5,8z"/>
  </svg>
</template>
        