
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiTetheringRound',
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
     xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"
  >
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M12 11c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm6 2c0-3.56-3.11-6.4-6.75-5.95-2.62.32-4.78 2.41-5.18 5.02-.33 2.15.49 4.11 1.93 5.4.48.43 1.23.33 1.56-.23l.01-.01c.24-.42.14-.93-.22-1.26-1.03-.93-1.59-2.37-1.22-3.94.33-1.42 1.48-2.57 2.9-2.91C13.65 8.49 16 10.47 16 13c0 1.18-.52 2.23-1.33 2.96-.36.32-.47.84-.23 1.26l.01.01c.31.53 1.03.69 1.5.28C17.2 16.41 18 14.8 18 13zm-7.17-9.93c-4.62.52-8.35 4.33-8.78 8.96-.35 3.7 1.32 7.02 4.02 9.01.48.35 1.16.2 1.46-.31.25-.43.14-.99-.26-1.29-2.28-1.69-3.65-4.55-3.16-7.7.54-3.5 3.46-6.29 6.98-6.68C15.91 4.51 20 8.28 20 13c0 2.65-1.29 4.98-3.27 6.44-.4.3-.51.85-.26 1.29.3.52.98.66 1.46.31C20.4 19.22 22 16.3 22 13c0-5.91-5.13-10.62-11.17-9.93z"/>
  </svg>
</template>
        