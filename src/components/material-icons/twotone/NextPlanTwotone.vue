
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NextPlanTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M12,4c-4.42,0-8,3.58-8,8s3.58,8,8,8s8-3.58,8-8S16.42,4,12,4z M13,14l2.26-2.26 C14.35,10.68,13.01,10,11.5,10c-2.37,0-4.35,1.66-4.86,3.88l-0.96-0.32C6.32,10.95,8.68,9,11.5,9c1.78,0,3.37,0.79,4.47,2.03L18,9 v5H13z" opacity=".3"/><path d="M12,2C6.48,2,2,6.48,2,12c0,5.52,4.48,10,10,10s10-4.48,10-10C22,6.48,17.52,2,12,2z M12,20c-4.42,0-8-3.58-8-8 s3.58-8,8-8s8,3.58,8,8S16.42,20,12,20z"/><path d="M15.97,11.03C14.87,9.79,13.28,9,11.5,9c-2.82,0-5.18,1.95-5.82,4.56l0.96,0.32C7.15,11.66,9.13,10,11.5,10 c1.51,0,2.85,0.68,3.76,1.74L13,14h5V9L15.97,11.03z"/></g></g>
  </svg>
</template>
        