
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FollowTheSignsTwotone',
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
    <rect fill="none" height="24" width="24"/><path d="M17.64,7.75V6h-3.51V4.5h3.51V2.75l2.49,2.5L17.64,7.75z" opacity=".3"/><path d="M9.12,5.25c1.1,0,2-0.9,2-2s-0.9-2-2-2s-2,0.9-2,2S8.02,5.25,9.12,5.25z M5.38,8.65l-2.75,14.1h2.1l1.75-8l2.15,2v6h2V15.2 l-2.05-2.05l0.6-3c1.3,1.6,3.25,2.6,5.45,2.6v-2c-1.85,0-3.45-1-4.35-2.45L9.32,6.7c-0.35-0.6-1-0.95-1.7-0.95 c-0.25,0-0.5,0.05-0.75,0.15L1.62,8.05v4.7h2V9.4L5.38,8.65 M12.62,1.75v7h3.75v14h1.5v-14h3.75v-7H12.62z M17.64,7.75V6h-3.51V4.5 h3.51V2.75l2.49,2.5L17.64,7.75z"/>
  </svg>
</template>
        