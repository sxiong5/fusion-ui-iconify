
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'OtherHousesRound',
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
    <rect fill="none" height="24" width="24"/><path d="M1.61,12.19c0.34,0.44,0.96,0.52,1.4,0.19L4,11.62V20c0,0.55,0.45,1,1,1h14c0.55,0,1-0.45,1-1v-8.38l0.99,0.76 c0.44,0.34,1.07,0.25,1.4-0.19c0.34-0.44,0.25-1.07-0.19-1.4l-9.6-7.33c-0.36-0.27-0.86-0.27-1.21,0l-9.6,7.33 C1.36,11.13,1.27,11.76,1.61,12.19z M8,15c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1s1,0.45,1,1C9,14.55,8.55,15,8,15z M12,15 c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1s1,0.45,1,1C13,14.55,12.55,15,12,15z M16,15c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1 s1,0.45,1,1C17,14.55,16.55,15,16,15z"/>
  </svg>
</template>
        