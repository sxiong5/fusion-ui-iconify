
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HdrAutoSelectTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><polygon points="22,18.5 22,16.5 20.5,16.5 20.5,18.5 18.5,18.5 18.5,20 20.5,20 20.5,22 22,22 22,20 24,20 24,18.5"/><polygon points="3.5,18 1.5,18 1.5,16 0,16 0,22 1.5,22 1.5,19.5 3.5,19.5 3.5,22 5,22 5,16 3.5,16"/><path d="M16.5,16H13v6h1.5v-2h1.1l0.9,2H18l-0.9-2.1c0.5-0.3,0.9-0.8,0.9-1.4v-1C18,16.7,17.3,16,16.5,16z M16.5,18.5h-2v-1h2 V18.5z"/><path d="M10,16H6.5v6H10c0.8,0,1.5-0.7,1.5-1.5v-3C11.5,16.7,10.8,16,10,16z M10,20.5H8v-3h2V20.5z"/><polygon points="11.97,5.3 10.95,8.19 13.05,8.19 12.03,5.3"/><path d="M12,2C8.69,2,6,4.69,6,8s2.69,6,6,6s6-2.69,6-6S15.31,2,12,2z M14.04,11l-0.63-1.79h-2.83L9.96,11H8.74l2.63-7h1.25 l2.63,7H14.04z"/></g></g>
  </svg>
</template>
        