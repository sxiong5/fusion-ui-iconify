
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EditNotificationsRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M17.58,6.25l1.77,1.77l-4.84,4.84C14.42,12.95,14.29,13,14.16,13H13.1c-0.28,0-0.5-0.22-0.5-0.5v-1.06 c0-0.13,0.05-0.26,0.15-0.35L17.58,6.25z M20.85,5.81l-1.06-1.06c-0.2-0.2-0.51-0.2-0.71,0l-0.85,0.85l1.77,1.77l0.85-0.85 C21.05,6.32,21.05,6,20.85,5.81z M20,18c0,0.55-0.45,1-1,1H5c-0.55,0-1-0.45-1-1s0.45-1,1-1h1v-7c0-2.79,1.91-5.14,4.5-5.8V3.5 C10.5,2.67,11.17,2,12,2s1.5,0.67,1.5,1.5v0.7c0.82,0.21,1.57,0.59,2.21,1.09l-4.52,4.52c-0.38,0.38-0.59,0.88-0.59,1.41V13 c0,1.1,0.9,2,2,2h1.77c0.53,0,1.04-0.21,1.41-0.59L18,12.2V17h1C19.55,17,20,17.45,20,18z M10,20h4c0,1.1-0.9,2-2,2S10,21.1,10,20z"/></g>
  </svg>
</template>
        