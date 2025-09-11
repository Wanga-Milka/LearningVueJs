<template>
  <div>
    {{ JSON.stringify(formValues,null,2) }}
  </div>
<label for="name">Name:</label>
<input type="text" id="name" v-model="formValues.name">
<label for="profile">Profile Summary</label>
<textarea  id="profile" v-model="formValues.profileSummary"></textarea>
<label for="country">Country</label>
<select  id="country" v-model="formValues.country">
  <option value="">Select Country</option>
  <option value="Kenya">Kenya</option>
  <option value="Uganda">Uganda</option>
  <option value="Tanzania">Tanzania</option>
  <option value="Engypt">Egypt</option>
  <option value="Ethiopia">Ethiopia</option>
  <option value="Somalia">Somalia</option>
</select>
  <!-- Select multiple values from drop down -->
   <p>Multiple selection on dropdown</p>
<label for="job-location">Job Location</label>
<select  id="job-location" multiple v-model="formValues.jobLocation"> 
  <option value="Kenya">Kenya</option>
  <option value="Uganda">Uganda</option>
  <option value="Tanzania">Tanzania</option>
  <option value="Engypt">Egypt</option>
  <option value="Ethiopia">Ethiopia</option>
  <option value="Somalia">Somalia</option>
</select>

</template>


<script>


export default {
  name: 'App',
  data()
  {
   return{
    formValues:{
      name:'',
      profileSummary:'',
      country:'',
      jobLocation: []
    }

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
