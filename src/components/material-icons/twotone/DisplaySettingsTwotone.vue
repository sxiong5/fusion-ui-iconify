
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DisplaySettingsTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M4,17h16V5H4V17z M18,13.75h-8v-1.5h8V13.75z M15,7h1.5v1.25H18v1.5h-1.5V11H15V7z M6,8.25h8v1.5H6V8.25z M6,12.25h1.5V11H9v4H7.5v-1.25H6V12.25z" opacity=".3"/><path d="M20,3H4C2.89,3,2,3.89,2,5v12c0,1.1,0.89,2,2,2h4v2h8v-2h4c1.1,0,2-0.9,2-2V5C22,3.89,21.1,3,20,3z M20,17H4V5h16V17z"/><rect height="1.5" width="8" x="6" y="8.25"/><polygon points="16.5,9.75 18,9.75 18,8.25 16.5,8.25 16.5,7 15,7 15,11 16.5,11"/><rect height="1.5" width="8" x="10" y="12.25"/><polygon points="7.5,15 9,15 9,11 7.5,11 7.5,12.25 6,12.25 6,13.75 7.5,13.75"/></g></g>
  </svg>
</template>
        