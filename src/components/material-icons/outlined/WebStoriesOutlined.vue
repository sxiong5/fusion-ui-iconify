
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WebStoriesOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M17,4v16c1.1,0,2-0.9,2-2V6C19,4.9,18.1,4,17,4z"/><path d="M13,2H4C2.9,2,2,2.9,2,4v16c0,1.1,0.9,2,2,2h9c1.1,0,2-0.9,2-2V4C15,2.9,14.1,2,13,2z M13,20H4V4h9V20z"/><path d="M21,6v12c0.83,0,1.5-0.67,1.5-1.5v-9C22.5,6.67,21.83,6,21,6z"/></g></g>
  </svg>
</template>
        