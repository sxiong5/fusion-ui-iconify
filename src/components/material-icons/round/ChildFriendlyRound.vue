
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ChildFriendlyRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M13 3.08V10h8c0-4.03-2.98-7.37-6.86-7.92-.6-.09-1.14.39-1.14 1zm6.32 12.81C20.37 14.54 21 12.84 21 11H6.44l-.68-1.43C5.6 9.22 5.24 9 4.86 9H3c-.55 0-1 .45-1 1s.45 1 1 1h1.22s1.89 4.07 2.12 4.42c-1.33.71-2.14 2.27-1.74 3.94.3 1.26 1.34 2.27 2.6 2.55 2.1.46 3.98-.96 4.25-2.91h2.08c.27 1.94 2.14 3.36 4.22 2.92 1.27-.27 2.31-1.27 2.63-2.53.35-1.39-.14-2.68-1.06-3.5zM8 20c-.83 0-1.5-.67-1.5-1.5S7.17 17 8 17s1.5.67 1.5 1.5S8.83 20 8 20zm9 0c-.83 0-1.5-.67-1.5-1.5S16.17 17 17 17s1.5.67 1.5 1.5S17.83 20 17 20z"/>
  </svg>
</template>
        