<template>
  <div class="home">
<div class="col">
  {{JSON.stringify(users)}}

  <button @click="useReduceMethod">Reduce</button>
  <button @click="reduceAlternate">Reduce</button>
  
  <div><h3>Modified data</h3></div>
  {{JSON.stringify(filteredUsers)}}
</div>

<div v-for="user in users" :key="user.age">

  <div>{{user.name}}</div>
</div>
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
  
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import reduce from 'lodash'
import _ from "lodash";

export default defineComponent({
  name: "HomeView",
  components: {
    HelloWorld,
  },
  setup(){
    const filteredUsers=ref<any>();
    var users = [
    { name: "John", age: 30 },
    { name: "Jane", age: 28 },
    { name: "Bill", age: 65 },
    { name: "Emily", age: 17 },
    { name: "Jack", age: 30 }
]

function reduceAlternate(){
  const apples = ['green', 'red', 'red', 'yellow', 'red', 'yellow', 'green', 'green'];

var appleMap = apples.reduce((prev:any, apple) => {
  if (prev[apple] >= 1) prev[apple]++;
  else prev[apple] = 1;
  return prev;
}, {});

console.log(appleMap)
}


//reduce
function useReduceMethod(){
  filteredUsers.value=_.reduce(users,function (result:any, user:any,key:any) {
    console.log('the key is ',key)
    console.log('the value is ',user)
    console.log('the result object is ',result)
    if(user.age >= 18 && user.age <= 59) {
      console.log('unknown ',result[user.age]);
        (result[user.age] || (result[user.age] = [])).push(user);
    }
  
    return result;
}, {})
}

    console.log('Inside the setup')
    return{
      users,filteredUsers,useReduceMethod,reduceAlternate
    }
  }
});
</script>
