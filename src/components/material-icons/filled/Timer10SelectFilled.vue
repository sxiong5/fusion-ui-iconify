
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'Timer10SelectFilled',
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
    <rect fill="none" height="24" width="24"/><path d="M13,8v8h-3V8H13 M13,5h-3C8.34,5,7,6.34,7,8v8c0,1.66,1.34,3,3,3h3c1.66,0,3-1.34,3-3V8C16,6.34,14.66,5,13,5z M1,8h2v11h3 V5H1V8z M18.5,11c-0.83,0-1.5,0.68-1.5,1.5v2c0,0.82,0.67,1.5,1.5,1.5H21v1h-4v2h4.5c0.83,0,1.5-0.67,1.5-1.5v-2 c0-0.83-0.67-1.5-1.5-1.5H19v-1h4v-2H18.5z"/>
  </svg>
</template>
        