
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RssFeedRound',
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
     xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"
  >
    <path d="M0 0h24v24H0V0z" fill="none"/><circle cx="6.18" cy="17.82" r="2.18"/><path d="M5.59 10.23c-.84-.14-1.59.55-1.59 1.4 0 .71.53 1.28 1.23 1.4 2.92.51 5.22 2.82 5.74 5.74.12.7.69 1.23 1.4 1.23.85 0 1.54-.75 1.41-1.59-.68-4.2-3.99-7.51-8.19-8.18zm-.03-5.71C4.73 4.43 4 5.1 4 5.93c0 .73.55 1.33 1.27 1.4 6.01.6 10.79 5.38 11.39 11.39.07.73.67 1.28 1.4 1.28.84 0 1.5-.73 1.42-1.56-.73-7.34-6.57-13.19-13.92-13.92z"/>
  </svg>
</template>
        