
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LibraryAddCheckRound',
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
    <path d="M20,2H8C6.9,2,6,2.9,6,4v12c0,1.1,0.9,2,2,2h12c1.1,0,2-0.9,2-2V4C22,2.9,21.1,2,20,2z M11.76,13.28L9.69,11.2 c-0.38-0.39-0.38-1.01,0-1.4l0,0c0.39-0.39,1.02-0.39,1.41,0l1.36,1.37l4.42-4.46c0.39-0.39,1.02-0.39,1.41,0l0,0 c0.38,0.39,0.38,1.01,0,1.4l-5.13,5.17C12.79,13.68,12.15,13.68,11.76,13.28z M3,6L3,6C2.45,6,2,6.45,2,7v13c0,1.1,0.9,2,2,2h13 c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H5c-0.55,0-1-0.45-1-1V7C4,6.45,3.55,6,3,6z"/><path d="M0,0h24v24H0V0z" fill="none"/>
  </svg>
</template>
        