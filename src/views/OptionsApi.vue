<template>
  <div class="about">
    <h1>Options Api Example</h1>
  </div>
<div class="row justify-center" style="padding:4px">Count :{{ count }}</div>
<div class="col">

  <button @click="increment" style="color:green;padding:4px;margin:4px"> Increase</button>
  <button @click="reduce" style="color:red;padding:4px;margin:4px">Decrease</button>
</div>

<div class="row justify-center q-pa-sm" style="padding:4px">{{alertMessage}}</div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
data(){
  return{
    firstName:ref('EA'),
    lastName:ref('Vijay'),
    count:ref(0)
  }
  
},
beforeMount(){
  alert('In the beforeMount method') 

},

mounted(){
 alert('In the mounted method') 
},
methods:{
increment(){
  this.count++;
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
    console.log('the old value is ',oldValue);
    console.log('the new value is ',newValue)
    if(this.count==20){
      alert('Exceeded maximum value ?')
    }
  }
}
})
</script>

