
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwitchAccessShortcutAddRound',
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
    <rect fill="none" height="24" width="24"/><path d="M21,18c0.55,0,1-0.45,1-1v-1h1c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1h-1v-1c0-0.55-0.45-1-1-1c-0.55,0-1,0.45-1,1v1h-1 c-0.55,0-1,0.45-1,1c0,0.55,0.45,1,1,1h1v1C20,17.55,20.45,18,21,18z M7.06,8.94L5,8l2.06-0.94L8,5l0.94,2.06L11,8L8.94,8.94L8,11 L7.06,8.94z M8,21l0.94-2.06L11,18l-2.06-0.94L8,15l-0.94,2.06L5,18l2.06,0.94L8,21z M4.37,12.37L3,13l1.37,0.63L5,15l0.63-1.37 L7,13l-1.37-0.63L5,11L4.37,12.37z M19,20.41c0,0.78-0.84,1.25-1.51,0.86C14.21,19.36,12,15.79,12,12c0-2.73,1.08-5.27,2.75-7.25 l-1.9-1.9C12.54,2.54,12.76,2,13.21,2h5.29C18.78,2,19,2.22,19,2.5v5.29c0,0.45-0.54,0.67-0.85,0.35l-1.97-1.97 C14.84,7.82,14,9.88,14,12c0,3.13,1.86,6.01,4.51,7.55C18.81,19.73,19,20.06,19,20.41z"/>
  </svg>
</template>
        