
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FormatColorResetOutlined',
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
    <path d="M0 0h24v24H0V0zm0 0h24v24H0V0zm0 0h24v24H0V0z" fill="none"/><path d="M12 6.36c1.53 2 3.08 4.43 3.71 6.24l2.23 2.23c.03-.27.06-.55.06-.83 0-3.98-6-10.8-6-10.8s-1.18 1.35-2.5 3.19l1.44 1.44c.34-.51.7-1 1.06-1.47zM5.41 5.14L4 6.55l3.32 3.32C6.55 11.33 6 12.79 6 14c0 3.31 2.69 6 6 6 1.52 0 2.9-.57 3.95-1.5l2.63 2.63L20 19.72 5.41 5.14zM12 18c-2.21 0-4-1.79-4-4 0-.69.32-1.62.81-2.64l5.72 5.72c-.7.56-1.57.92-2.53.92z"/>
  </svg>
</template>
        