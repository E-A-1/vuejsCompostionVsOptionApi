<template>
    <div style="height:50px;background-color:yellow"></div>
    <div style="min-height:calc(100vh - 100px);background-color:green">

        <div style="height:300px;border:2px solid red"></div>
        <div style="height:300px;border:2px solid red"></div>
        <div style="height:300px;border:2px solid red"></div>
        <div style="height:300px;border:2px solid red"></div>
    </div>
    <div style="height:50px;background-color:red;position:sticky"></div>
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

</style>
