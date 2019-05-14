<template>
  <div id="app">
     <input type="button" v-on:click="func(0)" value="Показать значения!"/>
  <ul class='list'>
     <li v-for="block in block1" v-bind:key="block.id">{{ block.type }} {{ block.a }} {{ block.b}} </li>
  </ul>
   <ul class='list'>
     <li v-for="block in block2" v-bind:key="block.id">{{ block.type }} {{ block.x }} {{block.n }} </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'app',

  data () {
    return  {
      block1 : [
          {id : 1, type : 'ADD', a : 0, b : 3}
          
      ] ,
      block2 : [
          {id : 2, type : 'MOD', x : 0, n : 16}
      ]     
    }
  },
  
 methods :  {
    func(a) {
    var b = 3;
    var n = 16;
    var x;
    for ( var i = 0; i < 10;  ) {
      x = a + b;
      a = x % n;
      i++;
      this.block1.push({id : 1, type : 'ADD', a : x , b : 3}),
      this.block2.push({id : 2, type : 'MOD', x : a , n : 16})
        
      
        //alert ("Шаг " + i + " /" + a + "  / " + b + " /" + x + " /" + n);
    }
    
      }
  }
}


</script>

<style>
#app {
  width: 200px;
  margin: 0 50px;

  }
</style>
