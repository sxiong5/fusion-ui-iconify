
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DeblurRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M12,3v18c4.97,0,9-4.03,9-9C21,7.03,16.97,3,12,3z"/><circle cx="6" cy="14" r="1"/><circle cx="6" cy="18" r="1"/><circle cx="6" cy="10" r="1"/><circle cx="3" cy="10" r=".5"/><circle cx="6" cy="6" r="1"/><circle cx="3" cy="14" r=".5"/><circle cx="10" cy="21" r=".5"/><circle cx="10" cy="3" r=".5"/><circle cx="10" cy="6" r="1"/><circle cx="10" cy="14" r="1.5"/><circle cx="10" cy="10" r="1.5"/><circle cx="10" cy="18" r="1"/></g></g>
  </svg>
</template>
        