
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BloodtypeRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M12.66,2.58c-0.38-0.33-0.95-0.33-1.33,0C6.45,6.88,4,10.62,4,13.8c0,4.98,3.8,8.2,8,8.2s8-3.22,8-8.2 C20,10.62,17.55,6.88,12.66,2.58z M14,18h-4c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h4c0.55,0,1,0.45,1,1C15,17.55,14.55,18,14,18z M14,13h-1v1c0,0.55-0.45,1-1,1s-1-0.45-1-1v-1h-1c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h1v-1c0-0.55,0.45-1,1-1s1,0.45,1,1v1h1 c0.55,0,1,0.45,1,1C15,12.55,14.55,13,14,13z"/></g>
  </svg>
</template>
        