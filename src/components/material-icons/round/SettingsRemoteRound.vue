
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SettingsRemoteRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M15,9H9c-0.55,0-1,0.45-1,1v12c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1V10C16,9.45,15.55,9,15,9z M12,14.25 c-0.69,0-1.25-0.56-1.25-1.25s0.56-1.25,1.25-1.25s1.25,0.56,1.25,1.25S12.69,14.25,12,14.25z"/><path d="M7.82,6.82L7.82,6.82c0.35,0.35,0.9,0.38,1.3,0.1C9.93,6.34,10.93,6,12,6c1.07,0,2.07,0.34,2.88,0.91 c0.4,0.28,0.95,0.26,1.3-0.09l0,0c0.43-0.43,0.39-1.15-0.09-1.5C14.94,4.49,13.53,4,12,4c-1.53,0-2.94,0.49-4.09,1.32 C7.42,5.67,7.39,6.39,7.82,6.82z"/><path d="M12,0C9.36,0,6.94,0.93,5.05,2.47c-0.46,0.38-0.5,1.07-0.08,1.49l0,0c0.36,0.36,0.93,0.39,1.32,0.07 C7.84,2.77,9.83,2,12,2c2.17,0,4.16,0.77,5.7,2.04c0.39,0.32,0.96,0.29,1.32-0.07l0,0c0.42-0.42,0.38-1.11-0.08-1.49 C17.06,0.93,14.64,0,12,0z"/></g></g>
  </svg>
</template>
        