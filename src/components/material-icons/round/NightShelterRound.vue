
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NightShelterRound',
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
    <rect fill="none" height="24" width="24"/><path d="M10.8,3.9l-6,4.5C4.3,8.78,4,9.37,4,10v9c0,1.1,0.9,2,2,2h12c1.1,0,2-0.9,2-2v-9c0-0.63-0.3-1.22-0.8-1.6l-6-4.5 C12.49,3.37,11.51,3.37,10.8,3.9z M9.75,12.5c0.69,0,1.25,0.56,1.25,1.25S10.44,15,9.75,15S8.5,14.44,8.5,13.75S9.06,12.5,9.75,12.5 z M16.5,18L16.5,18c-0.28,0-0.5-0.22-0.5-0.5v-1H8v1C8,17.78,7.78,18,7.5,18h0C7.22,18,7,17.78,7,17.5v-6C7,11.22,7.22,11,7.5,11h0 C7.78,11,8,11.22,8,11.5v4h3.5v-3c0-0.28,0.22-0.5,0.5-0.5h3c1.1,0,2,0.9,2,2v3.5C17,17.78,16.78,18,16.5,18z"/>
  </svg>
</template>
        