
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SevereColdOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon points="12,10.41 16,6.41 14.59,5 12,7.59 12,4 10,4 10,7.59 7.41,5 6,6.41 10,10.41 10,12 8.41,12 4.41,8 3,9.41 5.59,12 2,12 2,14 5.59,14 3,16.59 4.41,18 8.41,14 10,14 10,15.59 6,19.59 7.41,21 10,18.41 10,22 12,22 12,18.41 14.59,21 16,19.59 12,15.59 12,14 13.59,14 17.59,18 19,16.59 16.41,14 20,14 20,12 12,12"/><rect height="5" width="2" x="19" y="2"/><rect height="2" width="2" x="19" y="8"/></g></g>
  </svg>
</template>
        