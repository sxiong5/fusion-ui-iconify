
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AlignHorizontalCenterRound',
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
    <rect fill="none" height="24" width="24"/><path d="M12,2L12,2c0.55,0,1,0.45,1,1v4l6.5,0C20.33,7,21,7.67,21,8.5v0c0,0.83-0.67,1.5-1.5,1.5H13v4h3.5c0.83,0,1.5,0.67,1.5,1.5 v0c0,0.83-0.67,1.5-1.5,1.5H13v4c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v-4H7.5C6.67,17,6,16.33,6,15.5v0C6,14.67,6.67,14,7.5,14 H11v-4H4.5C3.67,10,3,9.33,3,8.5v0C3,7.67,3.67,7,4.5,7H11l0-4C11,2.45,11.45,2,12,2z"/>
  </svg>
</template>
        