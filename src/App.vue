<template>
  {{ count }}
  <button v-on:click="increment(1, $event)">Increment 1</button>
   <button v-on:click="increment(5, $event)">Increment 5</button>
   <button v-on:click="decrement(1, $event)">Decrement 1</button>
    <button @click="decrement(5, $event)">Decrement 5</button>
   
  <!-- Methods -->
   <h2>using base multiply->{{ multiply(3) }}</h2> 
   <h2>Add Method->{{ add(5,3,8) }}</h2>
  <!-- List Rendering -->
   <!-- list object -->
   <h2 v-for="(value,key,index) in objectDetails" :key="value">{{ index }} {{ key }} {{ value }}</h2>
   <!-- Array of objects -->
   <h2 v-for="firstName in fullNames" :key="firstName">{{ firstName.firstname }} {{ firstName.lastname }}</h2>
   <!-- Array of strings -->
   <h2 v-for="(fname,index) in names" :key="fname">{{index}} {{ fname }}</h2>
   <!-- Array of abject array -->
 <div v-for="actor in actors" :key="actor.actorname">
  <h2>{{ actor.actorname }}</h2>
  <h2 v-for="movie in actor.movies" :key="movie">{{ movie }}</h2>
 </div>

  <!-- Displays or hides element -->
  <div v-show="showElement">v-show</div>
  <!--  v-if Unmounts element from the dom if condition is false -->
  <div v-if="showElement">v-if</div>
  <!-- Use template instaed of div to avoid issues with html and css -->
  <template v-if="display">
    <h2>Codevolution</h2>
    <h2>VueJs</h2>
    <h2>Training</h2>
  </template>
  <div v-if="num===0">The number is zero</div>
  <div v-else-if="num<0">The number is negative</div>
  <div v-else-if="num>0">The number is positive</div>
  <div v-else>Not a number</div>
  <!-- binding text using interpolatiion -->
 <div> {{ greet }} {{ name }}</div>
 <button v-on:click="changeName">change name</button>

 <button v-on:mouseover="name='Batman'">change name</button>
 <hr>
 <!-- binding text using directive -->
 <div v-text="channel"></div>
 <div v-html="prac"></div>
 <div v-html="hack"></div>
 <div v-bind:id="headingId">Heading</div>
 <button v-bind:disabled="isDisabled">Bind</button>
 <div class="underline">Underline</div>
 <div v-bind:class="status" class="underline">status</div>
 <!-- if isPromoted is true apply class promoted -->
 <div v-bind:class="isPromoted && 'promoted' ">Front-end development</div>
 <div v-bind:class="isSoldout ? 'soldout' : 'new' ">Sandles</div>
 <h2 v-bind:class="['promoted','new']">Newly applied Movie</h2>
 <h2 v-bind:class="[isPromoted && 'promoted' , isSoldout ? 'soldout': 'new']"> Latest Movie</h2>
</template>


<script>


export default {
  name: 'App',
  data()
  {
    return {
      count:0,
    num:'Male',
      greet:"Good Morning",
      name: "Vishwas",    
      channel: "Codevolution",
      prac:`<b><i>Learning Vuejs tutorialspoint</b></i>`,
      hack:`<a href="#" onclick="alert('You have been attacked')">Win a prize!</a>`,
      headingId:"heading",
      isDisabled:false,
      status:'success',
      isPromoted:true,
      isSoldout:true,
      display:false,
      showElement:false,
      baseMultiplier:5,
      names:["Bruce","Isaac","John"],
      fullNames:[
        {firstname: "John",lastname:"Mike"},
        {firstname:"Agnes", lastname:"Kuria"},
        {firstname:"James",lastname:"kweyu"}
      ],
      actors:[
        {
          actorname:"neema Mbosso",
          movies:["Becky","Iron feast"]
        },
        {
          actorname:"Jayden Akimton",
          movies:["Maria","Sultana","Auras Quest"]
        }
      ],
      objectDetails:{
        studentname:"Mark",
        admission:"2019",
        class:"F2Q"
      }
      
    }
  },
    
  methods:{
    add(a,b,c)
    {
      return(a+b+c)
    },
     multiply(num)
     {
     return num * this.baseMultiplier;
    },
    increment(num,event)
    {
      this.count+= num
      console.log("Event",event);
      
    },
    decrement(num,event)
    {
       this.count-=num
       console.log("Event",event);
       
    },
    changeName(event)
    {
      
        this.name='Batman'
        console.log('Event',event);
        
      
    }
  },

 
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline{
  text-decoration: underline;
}
.promoted{
font-style: italic;
}
.soldout{
  color: red;
}
.new{
  color: green;
}

</style>
