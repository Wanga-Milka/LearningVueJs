<template>
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
</template>

<script>


export default {
  name: 'App',
  data()
  {
    return {
      greet:"Good Morning",
      name: "Vishwas",    
      channel: "Codevolution",
      prac:`<b><i>Learning Vuejs tutorialspoint</b></i>`,
      hack:`<a href="#" onclick="alert('You have been attacked')">Win a prize!</a>`,
      headingId:"heading",
      isDisabled:false,
      status:'success',
      isPromoted:true
      
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

</style>
