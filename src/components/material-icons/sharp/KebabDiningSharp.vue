
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'KebabDiningSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M7.75,8H11v5H7.75v1H8.5c1.38,0,2.5,1.12,2.5,2.5S9.88,19,8.5,19H7.75v4h-1.5v-4H5.5C4.12,19,3,17.88,3,16.5S4.12,14,5.5,14 h0.75v-1H3V8h3.25V7H5.5C4.12,7,3,5.88,3,4.5S4.12,2,5.5,2h0.75V1h1.5v1H8.5C9.88,2,11,3.12,11,4.5S9.88,7,8.5,7H7.75V8z M17.75,7 h0.75C19.88,7,21,5.88,21,4.5S19.88,2,18.5,2h-0.75V1h-1.5v1H15.5C14.12,2,13,3.12,13,4.5S14.12,7,15.5,7h0.75v1H13v5h3.25v1H15.5 c-1.38,0-2.5,1.12-2.5,2.5s1.12,2.5,2.5,2.5h0.75v4h1.5v-4h0.75c1.38,0,2.5-1.12,2.5-2.5S19.88,14,18.5,14h-0.75v-1H21V8h-3.25V7z"/>
  </svg>
</template>
        