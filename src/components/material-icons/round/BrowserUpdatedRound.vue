
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BrowserUpdatedRound',
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
    <rect fill="none" height="24" width="24" y="0"/><path d="M15,3c0.55,0,1,0.45,1,1v6h1.59c0.89,0,1.34,1.08,0.71,1.71l-2.59,2.59c-0.39,0.39-1.02,0.39-1.41,0l-2.59-2.59 C11.08,11.08,11.52,10,12.41,10H14V4C14,3.45,14.45,3,15,3z M6,19.59C6,20.37,6.63,21,7.41,21h9.17c0.78,0,1.41-0.63,1.41-1.41 c0-0.72-0.44-1.03-1-1.59h3c1.1,0,2-0.9,2-2v-2c0-0.55-0.45-1-1-1s-1,0.45-1,1v2H4V5l7,0c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1L4,3 C2.9,3,2,3.9,2,5v11c0,1.1,0.9,2,2,2h3C6.45,18.55,6,18.87,6,19.59z"/>
  </svg>
</template>
        