
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SettingsVoiceRound',
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
    <rect fill="none" height="24" width="24" y="0"/><path d="M8,24L8,24c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v0C7,23.55,7.45,24,8,24z M12,24L12,24 c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v0C11,23.55,11.45,24,12,24z M16,24L16,24c0.55,0,1-0.45,1-1v0 c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v0C15,23.55,15.45,24,16,24z M9,10V4c0-1.66,1.34-3,3-3s3,1.34,3,3v6c0,1.66-1.34,3-3,3 S9,11.66,9,10z M17.91,10c0.61,0,1.09,0.54,1,1.14c-0.49,3-2.89,5.34-5.91,5.78V19c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v-2.08 c-3.02-0.44-5.42-2.78-5.91-5.78c-0.1-0.6,0.39-1.14,1-1.14h0c0.49,0,0.9,0.36,0.98,0.85C7.48,13.21,9.53,15,12,15 s4.52-1.79,4.93-4.15C17.01,10.36,17.42,10,17.91,10L17.91,10z"/>
  </svg>
</template>
        