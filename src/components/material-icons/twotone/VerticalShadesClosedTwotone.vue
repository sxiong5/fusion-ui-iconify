
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VerticalShadesClosedTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><rect height="14" opacity=".2" width="1.5" x="9.5" y="5"/><rect height="14" opacity=".2" width="1.5" x="6" y="5"/><rect height="14" opacity=".2" width="1.5" x="13" y="5"/><rect height="14" opacity=".2" width="1.5" x="16.5" y="5"/><path d="M20,19V3H4v16H2v2h20v-2H20z M7.5,19H6V5h1.5V19z M11,19H9.5V5H11V19z M14.5,19H13V5h1.5V19z M18,19h-1.5V5H18V19z"/></g></g>
  </svg>
</template>
        