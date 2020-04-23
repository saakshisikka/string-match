<template>
  <div id="field">
  <div>
  <header>
   <p > Text 1: {{text1}}</p>
    <textarea v-model="text1" type="text" id="text1" placeholder="Enter first text" />
   
   </header>
   </div>
    <pre> </pre>
    
    <textarea v-model="text2" type="text" id="text2" placeholder="Enter Second text"/>
     <p >Text 2 : {{text2}}</p>
   <button v-on:click="check(text1, text2)">Check</button>
   
     <text-highlight :queries="str">{{ text2}}</text-highlight>

  </div>
   
</template>



<script>


export default {
  name: ' HelloWorld',
  data()
  {return {
      text1: '',
      text2: '',
     str:[''],
     
  }
  }, 
  
  methods: {
      check: function(text1, text2)
      { var str1 = text1.split(" ");
                var str2 = text2.split(" ");
                  var i = 0, j = 0;
                while(j < str2.length){
                    if (str1[i] !== str2[j]){
                        console.log(str2[j])
                        this.str.push(str2[j])
                    }
                    i++;
                    j++;
              
                }
                },
  },
};

  
     
  

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
