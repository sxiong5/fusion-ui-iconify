
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DoorbellOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M11,16.5h2c0,0.55-0.45,1-1,1S11,17.05,11,16.5z M15,15v-2.34c0-1.54-0.81-2.82-2.25-3.16V9.25c0-0.41-0.34-0.75-0.75-0.75 s-0.75,0.34-0.75,0.75V9.5C9.82,9.84,9,11.12,9,12.66V15H8v1h8v-1H15z M12,5.5L6,10v9h12v-9L12,5.5 M12,3l8,6v12H4V9L12,3z"/></g>
  </svg>
</template>
        