
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HomeRepairServiceTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M20,8h-3V6c0-1.1-0.9-2-2-2H9C7.9,4,7,4.9,7,6v2H4c-1.1,0-2,0.9-2,2v10h20V10C22,8.9,21.1,8,20,8z M9,6h6v2H9V6z M20,18 H4v-3h2v1h2v-1h8v1h2v-1h2V18z M20,13h-2v-1h-2v1H8v-1H6v1H4v-3h3h10h3V13z"/></g></g><g><g opacity=".3"><polygon points="18,16 16,16 16,15 8,15 8,16 6,16 6,15 4,15 4,18 20,18 20,15 18,15"/></g><g opacity=".3"><polygon points="4,10 4,13 6,13 6,12 8,12 8,13 16,13 16,12 18,12 18,13 20,13 20,10 17,10 7,10"/></g></g></g>
  </svg>
</template>
        