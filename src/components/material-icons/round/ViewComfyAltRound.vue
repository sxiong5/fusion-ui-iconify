
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ViewComfyAltRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M20,4H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6C22,4.9,21.1,4,20,4z M10.5,17h-3 C7.22,17,7,16.78,7,16.5v-3C7,13.22,7.22,13,7.5,13h3c0.28,0,0.5,0.22,0.5,0.5v3C11,16.78,10.78,17,10.5,17z M10.5,11h-3 C7.22,11,7,10.78,7,10.5v-3C7,7.22,7.22,7,7.5,7h3C10.78,7,11,7.22,11,7.5v3C11,10.78,10.78,11,10.5,11z M16.5,17h-3 c-0.28,0-0.5-0.22-0.5-0.5v-3c0-0.28,0.22-0.5,0.5-0.5h3c0.28,0,0.5,0.22,0.5,0.5v3C17,16.78,16.78,17,16.5,17z M16.5,11h-3 c-0.28,0-0.5-0.22-0.5-0.5v-3C13,7.22,13.22,7,13.5,7h3C16.78,7,17,7.22,17,7.5v3C17,10.78,16.78,11,16.5,11z"/></g></g>
  </svg>
</template>
        