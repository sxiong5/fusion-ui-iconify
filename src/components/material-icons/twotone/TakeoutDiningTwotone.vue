
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TakeoutDiningTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon opacity=".3" points="9.83,5 7.03,7.73 7.12,9 16.87,9 16.96,7.73 14.16,5"/><polygon opacity=".3" points="7.79,18 16.23,18 16.74,11 7.28,11"/><path d="M20.59,6.05L19,7.63l0.03-0.56L14.98,3H9.02L4.97,7.07L5,7.57L3.41,6.01L2,7.44l3.23,3.11L5.93,20h12.14l0.7-9.44L22,7.46 L20.59,6.05z M16.23,18H7.79l-0.51-7h9.46L16.23,18z M16.87,9H7.12L7.03,7.73L9.83,5h4.33l2.8,2.73L16.87,9z"/></g></g>
  </svg>
</template>
        