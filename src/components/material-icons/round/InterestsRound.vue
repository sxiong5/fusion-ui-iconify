
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'InterestsRound',
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
    <rect fill="none" height="24" width="24"/><path d="M7.02,13c-2.21,0-4,1.79-4,4s1.79,4,4,4s4-1.79,4-4S9.23,13,7.02,13z M13,14v6c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1v-6 c0-0.55-0.45-1-1-1h-6C13.45,13,13,13.45,13,14z M6.13,3.57l-3.3,5.94C2.46,10.18,2.94,11,3.7,11h6.6c0.76,0,1.24-0.82,0.87-1.49 l-3.3-5.94C7.49,2.89,6.51,2.89,6.13,3.57z M19.25,2.5c-1.06,0-1.81,0.56-2.25,1.17c-0.44-0.61-1.19-1.17-2.25-1.17 C13.19,2.5,12,3.78,12,5.25c0,1.83,2.03,3.17,4.35,5.18c0.37,0.32,0.92,0.32,1.3,0C19.97,8.42,22,7.08,22,5.25 C22,3.78,20.81,2.5,19.25,2.5z"/>
  </svg>
</template>
        