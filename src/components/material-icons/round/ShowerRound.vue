
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ShowerRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><circle cx="8" cy="17" r="1"/><circle cx="12" cy="17" r="1"/><circle cx="16" cy="17" r="1"/><path d="M13,5.08V4c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v1.08C7.61,5.57,5,8.47,5,12v1c0,0.55,0.45,1,1,1h12c0.55,0,1-0.45,1-1 v-1C19,8.47,16.39,5.57,13,5.08z"/><circle cx="8" cy="20" r="1"/><circle cx="12" cy="20" r="1"/><circle cx="16" cy="20" r="1"/></g>
  </svg>
</template>
        