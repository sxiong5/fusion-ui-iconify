
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EmergencyShareRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M12,9c-3.15,0-6,2.41-6,6.15c0,2.35,1.78,5.11,5.34,8.27c0.37,0.33,0.95,0.33,1.33,0C16.22,20.25,18,17.5,18,15.15 C18,11.41,15.15,9,12,9z M12,16.5c-0.83,0-1.5-0.67-1.5-1.5s0.67-1.5,1.5-1.5s1.5,0.67,1.5,1.5S12.83,16.5,12,16.5z M16.18,6.82 c-0.35,0.35-0.89,0.38-1.3,0.09C14.07,6.34,13.07,6,12,6S9.93,6.34,9.12,6.91c-0.41,0.28-0.95,0.26-1.3-0.09 c-0.43-0.43-0.39-1.15,0.09-1.5C9.06,4.49,10.48,4,12,4s2.94,0.49,4.09,1.32C16.58,5.67,16.61,6.39,16.18,6.82z M4.97,3.97 C4.55,3.54,4.59,2.85,5.05,2.47C6.95,0.93,9.37,0,12.01,0c2.64,0,5.06,0.93,6.95,2.48c0.46,0.38,0.5,1.07,0.08,1.49 c-0.36,0.36-0.93,0.39-1.32,0.07C16.16,2.77,14.17,2,12.01,2C9.83,2,7.84,2.77,6.29,4.04C5.9,4.36,5.33,4.32,4.97,3.97z"/></g>
  </svg>
</template>
        