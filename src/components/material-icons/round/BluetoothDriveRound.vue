
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BluetoothDriveRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M19.85,6l1.8-1.8c0.2-0.2,0.2-0.51,0-0.71L19.5,1.36c-0.32-0.31-0.85-0.09-0.85,0.35v3.08L16.7,2.85 c-0.19-0.19-0.51-0.19-0.7,0c-0.19,0.19-0.19,0.51,0,0.7L18.44,6L16,8.44c-0.19,0.19-0.19,0.5,0,0.7l0,0c0.19,0.2,0.51,0.2,0.7,0 l1.95-1.95v3.09c0,0.45,0.54,0.67,0.85,0.35l2.14-2.15c0.2-0.2,0.19-0.51,0-0.71L19.85,6z M19.65,2.91l0.94,0.94l-0.94,0.94V2.91z M19.65,9.08V7.2l0.94,0.94L19.65,9.08z"/><path d="M15,10H4.81l1.04-3H15V5H5.5C4.84,5,4.29,5.42,4.08,6.01L2,12v7.5C2,20.33,2.67,21,3.5,21S5,20.33,5,19.5V19h12v0.5 c0,0.83,0.67,1.5,1.5,1.5s1.5-0.67,1.5-1.5V12h-3C15.9,12,15,11.1,15,10z M6.5,16C5.67,16,5,15.33,5,14.5S5.67,13,6.5,13 S8,13.67,8,14.5S7.33,16,6.5,16z M15.5,16c-0.83,0-1.5-0.67-1.5-1.5s0.67-1.5,1.5-1.5s1.5,0.67,1.5,1.5S16.33,16,15.5,16z"/></g></g>
  </svg>
</template>
        