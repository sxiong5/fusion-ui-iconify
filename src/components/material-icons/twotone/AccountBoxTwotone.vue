
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AccountBoxTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M5,17.86C6.8,16.09,9.27,15,12,15s5.2,1.09,7,2.86V5H5V17.86z M12,6 c1.93,0,3.5,1.57,3.5,3.5S13.93,13,12,13c-1.93,0-3.5-1.57-3.5-3.5S10.07,6,12,6z" enable-background="new" opacity=".3"/><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M17,19H7v-0.24 C8.42,17.62,10.16,17,12,17s3.58,0.62,5,1.76V19z M19,17.86C17.2,16.09,14.73,15,12,15s-5.2,1.09-7,2.86V5h14V17.86z"/><path d="M12,13c1.93,0,3.5-1.57,3.5-3.5S13.93,6,12,6c-1.93,0-3.5,1.57-3.5,3.5S10.07,13,12,13z M12,8c0.83,0,1.5,0.67,1.5,1.5 S12.83,11,12,11s-1.5-0.67-1.5-1.5S11.17,8,12,8z"/></g></g>
  </svg>
</template>
        