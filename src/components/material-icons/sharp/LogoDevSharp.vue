
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LogoDevSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M7.68,14.98H6V9h1.71 c1.28,0,1.71,1.03,1.71,1.71l0,2.56C9.42,13.95,9,14.98,7.68,14.98z M12.38,11.46v1.07h-1.18v1.39h1.93v1.07h-2.25 c-0.4,0.01-0.74-0.31-0.75-0.71V9.75c-0.01-0.4,0.31-0.74,0.71-0.75h2.28l0,1.07h-1.92v1.39H12.38z M16.88,14.23 c-0.48,1.11-1.33,0.89-1.71,0L13.77,9h1.18l1.07,4.11L17.09,9h1.18L16.88,14.23z"/><path d="M7.77,10.12H7.14v3.77h0.63c0.14,0,0.28-0.05,0.42-0.16c0.14-0.1,0.21-0.26,0.21-0.47v-2.52c0-0.21-0.07-0.37-0.21-0.47 C8.05,10.17,7.91,10.12,7.77,10.12z"/></g></g>
  </svg>
</template>
        