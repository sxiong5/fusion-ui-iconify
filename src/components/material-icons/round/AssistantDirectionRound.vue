
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AssistantDirectionRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M13.5,10H9c-0.55,0-1,0.45-1,1v3c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h3.5v1.29c0,0.45,0.54,0.67,0.85,0.35 l2.29-2.29c0.2-0.2,0.2-0.51,0-0.71l-2.29-2.29c-0.31-0.31-0.85-0.09-0.85,0.35V10z M12,1C5.9,1,1,5.9,1,12s4.9,11,11,11 s11-4.9,11-11S18.1,1,12,1z M19.73,12.58l-7.19,7.22c-0.35,0.27-0.79,0.27-1.15,0L4.2,12.58c-0.27-0.36-0.27-0.8,0-1.16l7.19-7.22 c0.35-0.27,0.79-0.27,1.15,0l7.19,7.22C20.09,11.69,20.09,12.22,19.73,12.58z"/></g></g>
  </svg>
</template>
        