
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NineteenMpRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><rect height="1.5" width="1.5" x="13.5" y="6.5"/><path d="M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3z M7.75,5.5H9c0.55,0,1,0.45,1,1 v4.25c0,0.41-0.34,0.75-0.75,0.75S8.5,11.16,8.5,10.75V7H7.75C7.34,7,7,6.66,7,6.25S7.34,5.5,7.75,5.5z M12.5,17.75 c0,0.41-0.34,0.75-0.75,0.75S11,18.16,11,17.75V14h-1v2.25C10,16.66,9.66,17,9.25,17S8.5,16.66,8.5,16.25V14h-1v3.75 c0,0.41-0.34,0.75-0.75,0.75S6,18.16,6,17.75V13.5c0-0.55,0.45-1,1-1h4.5c0.55,0,1,0.45,1,1V17.75z M12,10.75 c0-0.41,0.34-0.75,0.75-0.75H15V9h-2c-0.55,0-1-0.45-1-1V6.5c0-0.55,0.45-1,1-1h2.5c0.55,0,1,0.45,1,1v4c0,0.55-0.45,1-1,1h-2.75 C12.34,11.5,12,11.16,12,10.75z M18,16c0,0.55-0.45,1-1,1h-2v0.75c0,0.41-0.34,0.75-0.75,0.75s-0.75-0.34-0.75-0.75V13.5 c0-0.55,0.45-1,1-1H17c0.55,0,1,0.45,1,1V16z"/><rect height="1.5" width="1.5" x="15" y="14"/></g></g>
  </svg>
</template>
        