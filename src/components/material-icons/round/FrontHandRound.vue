
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FrontHandRound',
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
    <rect fill="none" height="24" width="24"/><path d="M18.5,14.5c0,0.28-0.22,0.5-0.5,0.5l0,0c-1.51,0-2.77,1.12-2.97,2.58C15,17.82,14.78,18,14.54,18c-0.3,0-0.54-0.27-0.5-0.57 c0.26-1.77,1.68-3.17,3.46-3.4l0-10.78C17.5,2.56,16.94,2,16.25,2C15.56,2,15,2.56,15,3.25v7.25c0,0.28-0.22,0.5-0.5,0.5 S14,10.78,14,10.5V1.25C14,0.56,13.44,0,12.75,0S11.5,0.56,11.5,1.25v9.25c0,0.28-0.22,0.5-0.5,0.5s-0.5-0.22-0.5-0.5V2.75 c0-0.69-0.56-1.25-1.25-1.25S8,2.06,8,2.75v8.75C8,11.78,7.78,12,7.5,12S7,11.78,7,11.5V5.75C7,5.06,6.44,4.5,5.75,4.5 S4.5,5.06,4.5,5.75v10c0,4.56,3.69,8.25,8.25,8.25S21,20.31,21,15.75v-6.5C21,8.56,20.44,8,19.75,8S18.5,8.56,18.5,9.25V14.5z"/>
  </svg>
</template>
        