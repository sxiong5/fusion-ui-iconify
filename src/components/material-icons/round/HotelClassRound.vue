
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HotelClassRound',
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
    <rect fill="none" height="24" width="24"/><path d="M8.58 10H2.56c-.49 0-.69.62-.29.91l4.91 3.51-1.89 6.1c-.14.46.39.84.78.55L11 17.31l4.93 3.75c.39.29.92-.08.78-.55l-1.89-6.1 4.91-3.51c.4-.28.2-.91-.29-.91h-6.02l-1.95-6.42c-.14-.47-.81-.47-.96 0L8.58 10zM20.9 20.51l-1.4-4.52 2.91-2.08c.4-.28.2-.91-.29-.91h-1.88l-3.08 2.2 1.46 4.72 1.5 1.14c.39.29.92-.09.78-.55zM17 8l-1.34-4.42c-.14-.47-.81-.47-.96 0l-.57 1.87.78 2.55H17z"/>
  </svg>
</template>
        