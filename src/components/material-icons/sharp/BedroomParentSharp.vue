
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BedroomParentSharp',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><rect height="2" width="11" x="6.5" y="12"/><rect height="2" width="4" x="7.25" y="8.5"/><rect height="2" width="4" x="12.75" y="8.5"/><path d="M22,2H2v20h20V2z M19,17h-1.5v-1.5h-11V17H5v-5l0.65-0.55V7H11c0.37,0,0.72,0.12,1,0.32C12.28,7.12,12.63,7,13,7h5.35 v4.45L19,12V17z"/></g></g>
  </svg>
</template>
        