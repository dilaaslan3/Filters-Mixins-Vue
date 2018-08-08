<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <p>{{text | toUppercase | to-lowercase}}</p>
        <input v-model="filterText"/>
         <ul>
           <li v-for="fruit in filteredFruits">{{fruit}}</li>
         </ul>
        <button @click="fruits.push('Peach')">Add new Fruit</button>
        <hr>
        <app-list></app-list>
      </div>
    </div>
  </div>
</template>

<script>
  import List from './components/List.vue';
  import {fruitMixins} from "./fruitMixins";

  export default {
    mixins:[fruitMixins],
    data(){
      return{
        text:'Hello',
      }
    },
    filters:{
      toUppercase(value){
        return  value.toUpperCase();
      }
    },
    components:{
      appList:List
    }
  }
</script>

<style>

</style>
