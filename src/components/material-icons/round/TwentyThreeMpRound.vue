
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TwentyThreeMpRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M6.5,9c0-0.55,0.45-1,1-1h2V7H7.25 C6.84,7,6.5,6.66,6.5,6.25S6.84,5.5,7.25,5.5H10c0.55,0,1,0.45,1,1V8c0,0.55-0.45,1-1,1H8v1h2.25c0.41,0,0.75,0.34,0.75,0.75 s-0.34,0.75-0.75,0.75H7.5c-0.55,0-1-0.45-1-1V9z M12.5,17.75c0,0.41-0.34,0.75-0.75,0.75S11,18.16,11,17.75V14h-1v2.25 C10,16.66,9.66,17,9.25,17S8.5,16.66,8.5,16.25V14h-1v3.75c0,0.41-0.34,0.75-0.75,0.75S6,18.16,6,17.75V13.5c0-0.55,0.45-1,1-1 h4.5c0.55,0,1,0.45,1,1V17.75z M13,10.75c0-0.41,0.34-0.75,0.75-0.75H16V9h-1.5C14.22,9,14,8.78,14,8.5S14.22,8,14.5,8H16V7h-2.25 C13.34,7,13,6.66,13,6.25s0.34-0.75,0.75-0.75h2.75c0.55,0,1,0.45,1,1v4c0,0.55-0.45,1-1,1h-2.75C13.34,11.5,13,11.16,13,10.75z M18,16c0,0.55-0.45,1-1,1h-2v0.75c0,0.41-0.34,0.75-0.75,0.75s-0.75-0.34-0.75-0.75V13.5c0-0.55,0.45-1,1-1H17c0.55,0,1,0.45,1,1 V16z"/><rect height="1.5" width="1.5" x="15" y="14"/></g></g>
  </svg>
</template>
        