
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HvacOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M19,19H5V5h14V19z"/><path d="M12,18c3.31,0,6-2.69,6-6s-2.69-6-6-6s-6,2.69-6,6S8.69,18,12,18z M15.44,10c0.26,0.45,0.44,0.96,0.51,1.5h-7.9 c0.07-0.54,0.24-1.05,0.51-1.5H15.44z M15.95,12.5c-0.07,0.54-0.24,1.05-0.51,1.5H8.56c-0.26-0.45-0.44-0.96-0.51-1.5H15.95z M9.38,15h5.24c-0.7,0.61-1.61,1-2.62,1S10.09,15.61,9.38,15z M14.62,9H9.38c0.7-0.61,1.61-1,2.62-1S13.91,8.39,14.62,9z"/></g></g>
  </svg>
</template>
        