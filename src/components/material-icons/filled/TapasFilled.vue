
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TapasFilled',
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
    <rect fill="none" height="24" width="24"/><path d="M22,10V1h-8v9c0,1.86,1.28,3.41,3,3.86V21h-2v2h6v-2h-2v-7.14C20.72,13.41,22,11.86,22,10z M20,3v3h-4V3H20z M12.5,11.5 c0,1.38-1.12,2.5-2.5,2.5H8v9H6v-9H4c-1.38,0-2.5-1.12-2.5-2.5C1.5,10.12,2.62,9,4,9h2V8H4C2.62,8,1.5,6.88,1.5,5.5 C1.5,4.12,2.62,3,4,3h2V1h2v2h2c1.38,0,2.5,1.12,2.5,2.5C12.5,6.88,11.38,8,10,8H8v1h2C11.38,9,12.5,10.12,12.5,11.5z"/>
  </svg>
</template>
        