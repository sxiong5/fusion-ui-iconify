
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FlashlightOffTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><g><polygon opacity=".3" points="16,7 9.83,7 14,11.17 14,10.4 16,7.39"/><polygon opacity=".3" points="10,12.83 10,20 14,20 14,16.83"/><polygon opacity=".3" points="16,5 16,4 6.83,4 7.83,5"/></g><g><path d="M2.81,2.81L1.39,4.22L8,10.83V22h8v-3.17l3.78,3.78l1.41-1.41L2.81,2.81z M14,20h-4v-7.17l4,4V20z"/><polygon points="16,4 16,5 7.83,5 9.83,7 16,7 16,7.39 14,10.4 14,11.17 16,13.17 16,11 18,8 18,2 6,2 6,3.17 6.83,4"/></g></g></g>
  </svg>
</template>
        