
<template>
  <div>
    {{ JSON.stringify(formValues,null,2) }}
  </div>
<form @submit="submitForm">
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
 <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
 <label for="remote">Work from home</label>
 <label for="skillset">Skill Set</label>
 <input type="checkbox"  id="html" value="html" v-model="formValues.skillset">
 <label for="html">HTML</label>
  <input type="checkbox"  id="css" value="css" v-model="formValues.skillset">
 <label for="html">CSS</label>
   <input type="checkbox"  id="javascript" value="javascript" v-model="formValues.skillset">
 <label for="javascript">Javascript</label>
 <label for="yearsofexperience">Years Of Experience</label>
 <input type="radio"  id="0-2" value="0-2" v-model="formValues.yearsofexperience">
 <label for="0-2">0-2years</label>
  <input type="radio"  id="3-5"  value="3-5" v-model="formValues.yearsofexperience">
 <label for="3-5">3-5 years</label>
  <input type="radio"  id="6-8" value="6-8" v-model="formValues.yearsofexperience">
 <label for="6-8">6-8 years</label>
 <button>submit</button>
</form>
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
      jobLocation: [],
      remoteWork:"no",
      skillset: [],
      yearsofexperience:'',
 

    }

   }
  },
  methods:{
    submitForm(event)
    {
      event.preventDefault();
      console.log('Form Values',this.formValues);
      
    }
  }

    
 

 
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
