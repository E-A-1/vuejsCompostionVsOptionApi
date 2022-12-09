<!-- eslint-disable vue/multi-word-component-names -->
// eslint-disable-next-line vue/multi-word-component-names
<template>
  <div class="">
    <slot name="header"></slot>

    <div class="row justify-center" style="color: purple">
      <h3>Count value</h3>
    </div>
    <div class="row justify-center">
      <span style="background-color: blanchedalmond">
        {{ count }}
      </span>
    </div>
    <div class="row justify-center" style="margin-top: 8px">
      <button @click="clearValue">clear</button>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    count: {
      type: Number,
      required: true,
      
    },
  },
 emits:['clear'],

  setup(props, context) {

    function clearValue() {
        console.log('------Event emitted ---------')
      context.emit("clear",);
    }

    return {
      clearValue,
    };
  },
});
</script>
