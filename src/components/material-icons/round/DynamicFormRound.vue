
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DynamicFormRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M21.68,9.71l-3.72,8.19C17.73,18.39,17,18.23,17,17.69V11h-1.5c-0.28,0-0.5-0.22-0.5-0.5v-6C15,4.22,15.22,4,15.5,4h5.76 c0.35,0,0.6,0.36,0.46,0.69L20,9h1.22C21.59,9,21.83,9.38,21.68,9.71z M15,13v7H4c-1.1,0-2-0.9-2-2v-3c0-1.1,0.9-2,2-2H15z M6.25,16.5c0-0.41-0.34-0.75-0.75-0.75s-0.75,0.34-0.75,0.75c0,0.41,0.34,0.75,0.75,0.75S6.25,16.91,6.25,16.5z M13,4v7H4 c-1.1,0-2-0.9-2-2V6c0-1.1,0.9-2,2-2H13z M6.25,7.5c0-0.41-0.34-0.75-0.75-0.75S4.75,7.09,4.75,7.5c0,0.41,0.34,0.75,0.75,0.75 S6.25,7.91,6.25,7.5z"/></g>
  </svg>
</template>
        