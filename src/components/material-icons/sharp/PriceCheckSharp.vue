
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PriceCheckSharp',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><polygon points="11,8 6,8 6,6 11,6 11,4 8.5,4 8.5,3 6.5,3 6.5,4 4,4 4,10 9,10 9,12 4,12 4,14 6.5,14 6.5,15 8.5,15 8.5,14 11,14"/><polygon points="19.59,12.52 13.93,18.17 11.1,15.34 9.69,16.76 13.93,21 21,13.93"/></g></g>
  </svg>
</template>
        