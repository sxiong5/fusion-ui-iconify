
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DevicesFoldSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M17,3v-3.03l-7,3V3v18h12V3H17z M20,19h-5.33L17,18V5h3V19z"/></g><g><rect height="2" width="2" x="2" y="3"/></g><g><rect height="2" width="2" x="2" y="19"/></g><g><rect height="2" width="2" x="2" y="15"/></g><g><rect height="2" width="2" x="2" y="11"/></g><g><rect height="2" width="2" x="2" y="7"/></g><g><rect height="2" width="2" x="6" y="3"/></g><g><rect height="2" width="2" x="6" y="19"/></g></g></g>
  </svg>
</template>
        