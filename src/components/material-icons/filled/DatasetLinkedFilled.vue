
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DatasetLinkedFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M8.09,17H7v-4h3.69c0.95-0.63,2.09-1,3.31-1h6c0.34,0,0.67,0.04,1,0.09V5c0-1.1-0.9-2-2-2H5C3.9,3,3,3.9,3,5v14 c0,1.1,0.9,2,2,2h3.81C8.3,20.12,8,19.09,8,18C8,17.66,8.04,17.33,8.09,17z M13,7h4v4h-4V7z M7,7h4v4H7V7z"/><path d="M12,18c0-1.1,0.9-2,2-2h2v-2h-2c-2.21,0-4,1.79-4,4c0,2.21,1.79,4,4,4h2v-2h-2C12.9,20,12,19.1,12,18z"/><path d="M20,14h-2v2h2c1.1,0,2,0.9,2,2s-0.9,2-2,2h-2v2h2c2.21,0,4-1.79,4-4C24,15.79,22.21,14,20,14z"/><rect height="2" width="6" x="14" y="17"/></g></g>
  </svg>
</template>
        