<template>
  <div v-if="false"></div>
  <div class="about" v-else>
    <h1>Options Api Example</h1>
  </div>
<card-vue :count="count" v-on:clear="clearCountValue"></card-vue>
<div class="col" style="padding:2rem">

  <button @click="increment" style="color:green;padding:4px;margin:4px"> Increase</button>
  <button @click="reduce" style="color:red;padding:4px;margin:4px">Decrease</button>
</div>

<div class="row justify-center q-pa-sm" style="padding:4px">{{alertMessage}}</div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import CardVue from '@/components/Card.vue'
export default defineComponent({
  components:{CardVue},
data(){
  return{
    firstName:ref('EA'),
    lastName:ref('Vijay'),
    count:0
  }
  
},
beforeMount(){
  alert('In the options api beforeMount method') 

},

mounted(){
 alert('In the options api mounted method') 
},

methods:{
increment(){
  this.count++;
},
clearCountValue(){
this.count=0;
},
reduce(){
  this.count--;
}

},

computed:{
 
  alertMessage(){
  if(this.count>15){
return 'Count Value is High'
  }else if(this.count<10){
return 'Count Value is Low';
  }else{
    return 'Count Value is Medium'
  }
  }

},

watch:{
  count(newValue,oldValue){
   
    if(this.count==20){
      alert('Exceeded maximum value ?')
    }
  }
}
})
</script>

