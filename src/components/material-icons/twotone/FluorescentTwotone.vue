
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FluorescentTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><rect height="2" opacity=".3" width="10" x="7" y="11"/><path d="M5,15h14V9H5V15z M7,11h10v2H7V11z"/><rect height="3" width="2" x="11" y="2"/><rect height="2" transform="matrix(0.7046 -0.7096 0.7096 0.7046 1.1814 15.2381)" width="2.54" x="17.62" y="5.2"/><rect height="3" width="2" x="11" y="19"/><polygon points="17.29,17.71 19.08,19.51 20.5,18.09 18.7,16.3"/><rect height="2.53" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -2.8904 5.4222)" width="1.99" x="4.1" y="4.93"/><rect height="2" transform="matrix(0.7096 -0.7046 0.7046 0.7096 -11.1263 8.7897)" width="2.54" x="3.83" y="16.89"/></g></g>
  </svg>
</template>
        