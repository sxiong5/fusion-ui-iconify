
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LightbulbCircleTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M12,4c-4.41,0-8,3.59-8,8s3.59,8,8,8s8-3.59,8-8S16.41,4,12,4z M12,19c-0.83,0-1.5-0.67-1.5-1.5h3 C13.5,18.33,12.83,19,12,19z M15,16.5H9V15h6V16.5z M14.97,14H9.03C7.8,13.09,7,11.64,7,10c0-2.76,2.24-5,5-5s5,2.24,5,5 C17,11.64,16.2,13.09,14.97,14z" opacity=".3"/><path d="M12,2C6.48,2,2,6.48,2,12s4.48,10,10,10s10-4.48,10-10S17.52,2,12,2z M12,20c-4.41,0-8-3.59-8-8s3.59-8,8-8s8,3.59,8,8 S16.41,20,12,20z"/><path d="M12,19c0.83,0,1.5-0.67,1.5-1.5h-3C10.5,18.33,11.17,19,12,19z"/><rect height="1.5" width="6" x="9" y="15"/><path d="M12,5c-2.76,0-5,2.24-5,5c0,1.64,0.8,3.09,2.03,4h5.95C16.2,13.09,17,11.64,17,10C17,7.24,14.76,5,12,5z M14.43,12.5H9.57 C8.89,11.84,8.5,10.95,8.5,10c0-1.93,1.57-3.5,3.5-3.5s3.5,1.57,3.5,3.5C15.5,10.95,15.11,11.84,14.43,12.5z"/></g></g>
  </svg>
</template>
        