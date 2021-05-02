<template>
  <div id="app">
    <input type="text" v-model="code">
    <button @click="seachPost">住所自動検索</button>
    <p>Address:{{addressData}}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'App',
  data(){
    return{
      code : "",
      addressData:[]
    };
  },
  methods:{
    async seachPost(){
       await axios.get('https://apis.postcode-jp.com/api/v4/postcodes/{this.code}?apiKey=Cpar2ZfylzfplDbwHNzLAIeIg9eSwByGnpcEpzc')
       .then(response=>(this.addressData=response))    
       console.log(this.addressData);
    }
  }
}
</script>

<style>
</style>
