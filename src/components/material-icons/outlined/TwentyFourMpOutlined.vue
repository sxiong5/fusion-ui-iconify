
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TwentyFourMpOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M7.5,14h1v3H10v-3h1v4.5h1.5v-5c0-0.55-0.45-1-1-1H7c-0.55,0-1,0.45-1,1v5h1.5V14z"/><path d="M17,12.5h-3.5v6H15V17h2c0.55,0,1-0.45,1-1v-2.5C18,12.95,17.55,12.5,17,12.5z M16.5,15.5H15V14h1.5V15.5z"/><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M19,19H5V5h14V19z"/><path d="M11,10H8V9h2c0.55,0,1-0.45,1-1V6.5c0-0.55-0.45-1-1-1H6.5V7h3v1h-2c-0.55,0-1,0.45-1,1v2.5H11V10z"/><polygon points="16,11.5 17.5,11.5 17.5,10 18.5,10 18.5,8.5 17.5,8.5 17.5,5.5 16,5.5 16,8.5 14.5,8.5 14.5,5.5 13,5.5 13,10 16,10"/></g></g>
  </svg>
</template>
        