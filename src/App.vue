<template>
  <div id="app">
    <input type="number" v-model="code">
    <button @click="seachPost()">住所自動検索</button>
    <p>Address:{{addressData}}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'App',
  data(){
    return{
      code : ""
    };
  },
  methods:{
    async seachPost(){
      const postcode = await axios.get('https://apis.postcode-jp.com/api/v4/postcodes/{code}?apiKey=Cpar2ZfylzfplDbwHNzLAIeIg9eSwByGnpcEpzc');

      const addressData = postcode;      
      }
  }
}
</script>

<style>
</style>
