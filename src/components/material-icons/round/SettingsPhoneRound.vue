
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SettingsPhoneRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><circle cx="12" cy="10" r="1"/><circle cx="16" cy="10" r="1"/><circle cx="20" cy="10" r="1"/><path d="M15.63,14.4l-2.52,2.5c-2.5-1.43-4.57-3.5-6-6l2.5-2.52c0.23-0.24,0.33-0.57,0.27-0.9L9.13,3.8C9.04,3.34,8.63,3,8.15,3 L4,3C3.44,3,2.97,3.47,3,4.03C3.17,6.92,4.05,9.63,5.43,12c1.58,2.73,3.85,4.99,6.57,6.57c2.37,1.37,5.08,2.26,7.97,2.43 c0.56,0.03,1.03-0.44,1.03-1l0-4.15c0-0.48-0.34-0.89-0.8-0.98l-3.67-0.73C16.2,14.07,15.86,14.17,15.63,14.4z"/></g></g>
  </svg>
</template>
        