
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AnimationOutlined',
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
    <g><rect fill="none" height="24" width="24" x="0"/></g><g><g><path d="M15,2c-2.71,0-5.05,1.54-6.22,3.78c-1.28,0.67-2.34,1.72-3,3C3.54,9.95,2,12.29,2,15c0,3.87,3.13,7,7,7 c2.71,0,5.05-1.54,6.22-3.78c1.28-0.67,2.34-1.72,3-3C20.46,14.05,22,11.71,22,9C22,5.13,18.87,2,15,2z M9,20c-2.76,0-5-2.24-5-5 c0-1.12,0.37-2.16,1-3c0,3.87,3.13,7,7,7C11.16,19.63,10.12,20,9,20z M12,17c-2.76,0-5-2.24-5-5c0-1.12,0.37-2.16,1-3 c0,3.86,3.13,6.99,7,7C14.16,16.63,13.12,17,12,17z M16.7,13.7C16.17,13.89,15.6,14,15,14c-2.76,0-5-2.24-5-5 c0-0.6,0.11-1.17,0.3-1.7C10.83,7.11,11.4,7,12,7c2.76,0,5,2.24,5,5C17,12.6,16.89,13.17,16.7,13.7z M19,12c0-3.86-3.13-6.99-7-7 c0.84-0.63,1.87-1,3-1c2.76,0,5,2.24,5,5C20,10.12,19.63,11.16,19,12z"/></g></g>
  </svg>
</template>
        