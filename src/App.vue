<template>
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
      showElement:false
      
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
