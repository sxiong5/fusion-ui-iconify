
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MedicalInformationRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M20,7h-5V4c0-1.1-0.9-2-2-2h-2C9.9,2,9,2.9,9,4v3H4C2.9,7,2,7.9,2,9v11c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V9 C22,7.9,21.1,7,20,7z M11,4h2v5h-2V4z M7,16H6c-0.55,0-1-0.45-1-1s0.45-1,1-1h1v-1c0-0.55,0.45-1,1-1s1,0.45,1,1v1h1 c0.55,0,1,0.45,1,1s-0.45,1-1,1H9v1c0,0.55-0.45,1-1,1s-1-0.45-1-1V16z M13.75,14.5c-0.41,0-0.75-0.34-0.75-0.75S13.34,13,13.75,13 h4.5c0.41,0,0.75,0.34,0.75,0.75s-0.34,0.75-0.75,0.75H13.75z M13.75,17.5c-0.41,0-0.75-0.34-0.75-0.75S13.34,16,13.75,16h2.5 c0.41,0,0.75,0.34,0.75,0.75s-0.34,0.75-0.75,0.75H13.75z"/></g>
  </svg>
</template>
        