
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AcUnitRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M21 11h-3.17l2.54-2.54c.39-.39.39-1.02 0-1.41-.39-.39-1.03-.39-1.42 0L15 11h-2V9l3.95-3.95c.39-.39.39-1.03 0-1.42-.39-.39-1.02-.39-1.41 0L13 6.17V3c0-.55-.45-1-1-1s-1 .45-1 1v3.17L8.46 3.63c-.39-.39-1.02-.39-1.41 0-.39.39-.39 1.03 0 1.42L11 9v2H9L5.05 7.05c-.39-.39-1.03-.39-1.42 0-.39.39-.39 1.02 0 1.41L6.17 11H3c-.55 0-1 .45-1 1s.45 1 1 1h3.17l-2.54 2.54c-.39.39-.39 1.02 0 1.41.39.39 1.03.39 1.42 0L9 13h2v2l-3.95 3.95c-.39.39-.39 1.03 0 1.42.39.39 1.02.39 1.41 0L11 17.83V21c0 .55.45 1 1 1s1-.45 1-1v-3.17l2.54 2.54c.39.39 1.02.39 1.41 0 .39-.39.39-1.03 0-1.42L13 15v-2h2l3.95 3.95c.39.39 1.03.39 1.42 0 .39-.39.39-1.02 0-1.41L17.83 13H21c.55 0 1-.45 1-1s-.45-1-1-1z"/>
  </svg>
</template>
        