<template>
  
  <div class="m-auto">
   <h1 class="text-4xl text-center">To Do  {{herosCount}} </h1>
   <ul>
      <li class="flex justify-between" v-for="(hero, index) in dcHeros" v-bind:key="hero.name">{{ hero.name }} 
       
         <button v-on:click="remove(index)">x</button>
     
      </li>
       
   </ul>
   
   <form  class="mt-10"
       @submit.prevent="addHero"> 

     <input class="border rounded" v-model="newHero" placeholder="Type To Do Name Here" />
     <button class="border rounded bg-gradient-to-r from-red-700 to-pink-500 text-sm text-white w-20 " type="submit">Add To Do</button>
   </form>
   <small>How many to do in the List: {{herosCount}}</small>
</div>

</template>

<script>
export default {
    data() {
    return {
    
      newHero: "",
      dcHeros : [
      { name:"Wake UP" },
      { name:"Drink Coffe" },
      { name:"More Code" },
      { name:"Go Out" },
      { name:"Take a breath" }],
    };
  },
   computed: {
    herosCount() {
      return this.dcHeros.length;
    },
  },
  methods: {
      addHero() {
        if (this.newHero != "") { 
         this.dcHeros.unshift({ name: this.newHero });
         this.newHero = '';
         }
      },
     remove(index) {
      this.dcHeros = this.dcHeros.filter((hero,i) => i != index)
     },
  },
}
</script>

<style>

</style>