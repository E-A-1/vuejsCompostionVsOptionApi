<template>
    <div style="height:50px;background-color:yellow"></div>
    <div style="min-height:calc(100vh - 100px);background-color:green">

        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
    </div>
    <div style="height:50px;background-color:red;"></div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    setup() {
        //
    },
})
</script>
<style scoped>
.box{
    height:300px;border:2px solid red
}
</style>
