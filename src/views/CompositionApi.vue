<template>
    <div class="about">
        <h1>Composition Api Example</h1>
      </div>
    
      <card-vue :count="count" v-on:clear="count=0"></card-vue>
<div class="col" style="padding:2rem">

  <button @click="increment" style="color:green;padding:4px;margin:4px"> Increase</button>
  <button @click="reduce" style="color:red;padding:4px;margin:4px">Decrease</button>
</div>

<div class="content_style" style="width:100%">
    <div  style="padding:20px;border:2px solid #f5f5f5;width:50%;background-color:#f5f5f5"> {{alertMessage}} </div>
   </div>
</template>
<script lang="ts">
import { computed, defineComponent, onBeforeMount, onMounted, ref, watch } from 'vue'
import CardVue from '@/components/Card.vue'

export default defineComponent({
    components:{CardVue},

    setup() {
      
        const firstName=ref('EA');
        const lastName=ref('Vijay');
        const count=ref(0);
function increment(){
    count.value++;
}
function reduce(){
    count.value--;
}
const alertMessage=computed(()=>{
    if(count.value>15){
        return 'Count Value is High'
  }else if(count.value<10){
    return 'Count Value is Low';
  }else{
return 'Count Value is Medium'

  }
});

onBeforeMount(()=>{
    alert('Inside the composition api onBefore mount method')
})

onMounted(()=>{

    alert('Inside the composition api onMounted method')
})

watch (count,(newValue,oldValue)=>{
if(newValue==20){
    alert('Exceeded maximum value ?')

}
})

return{
    firstName,
    lastName,
    increment,
    reduce,
    alertMessage,count

}

    },
})
</script>
<style scoped>
.content_style{
 
   display: flex;
   place-items:center;
   justify-content: center;
}
</style>