
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CarRentalFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M16.39,9H7.61C7.18,9,6.8,9.28,6.66,9.68l-1.66,5v6.81C5,21.78,5.23,22,5.5,22h1C6.78,22,7,21.78,7,21.5V20h10v1.5 c0,0.28,0.22,0.5,0.5,0.5h1c0.28,0,0.5-0.22,0.5-0.5v-6.81l-1.66-5C17.2,9.28,16.82,9,16.39,9z M7.78,18 c-0.68,0-1.22-0.54-1.22-1.22s0.54-1.22,1.22-1.22S9,16.11,9,16.78S8.46,18,7.78,18z M16.22,18C15.55,18,15,17.46,15,16.78 s0.54-1.22,1.22-1.22s1.22,0.54,1.22,1.22S16.9,18,16.22,18z M6.29,14l1.33-4h8.78l1.33,4H6.29z"/><path d="M10.83,3C10.41,1.83,9.3,1,8,1C6.34,1,5,2.34,5,4c0,1.65,1.34,3,3,3c1.3,0,2.41-0.84,2.83-2H16v2h2V5h1V3H10.83z M8,5 C7.45,5,7,4.55,7,4s0.45-1,1-1s1,0.45,1,1S8.55,5,8,5z"/></g></g>
  </svg>
</template>
        