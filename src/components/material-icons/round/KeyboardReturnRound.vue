
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'KeyboardReturnRound',
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
    <path d="M19 8v3H5.83l2.88-2.88c.39-.39.39-1.02 0-1.41-.39-.39-1.02-.39-1.41 0L2.71 11.3c-.39.39-.39 1.02 0 1.41L7.3 17.3c.39.39 1.02.39 1.41 0 .39-.39.39-1.02 0-1.41L5.83 13H20c.55 0 1-.45 1-1V8c0-.55-.45-1-1-1s-1 .45-1 1z"/>
  </svg>
</template>
        