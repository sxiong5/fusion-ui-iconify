
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FoodBankTwotone',
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
    <rect fill="none" height="24" width="24"/><path d="M12,5.5l6,4.5v9H6v-9L12,5.5 M11.5,9.5v3H11v-3h-1v3H9.5v-3h-1v3c0,0.83,0.67,1.5,1.5,1.5v4h1v-4 c0.83,0,1.5-0.67,1.5-1.5v-3H11.5z M13,11.5v3h1V18h1V9.5C13.9,9.5,13,10.4,13,11.5z" opacity=".3"/><path d="M12,5.5l6,4.5v9H6v-9L12,5.5 M12,3L4,9v12h16V9L12,3L12,3z M11.5,9.5v3H11v-3h-1v3H9.5v-3h-1v3c0,0.83,0.67,1.5,1.5,1.5v4h1 v-4c0.83,0,1.5-0.67,1.5-1.5v-3H11.5z M13,11.5v3h1V18h1V9.5C13.9,9.5,13,10.4,13,11.5z"/>
  </svg>
</template>
        