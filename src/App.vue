<!-- ignore the common event handling like don’t reload the page when the form is submitted and other similar issues. 
  Event Modifiers allow to handle them in the DOM itself. We don’t need to create any new components for these purposes.-->
  <!--we can add key modifiers that allow us to listen to a particular key when handling key-related events such as keyup.-->
<template>
  <div id="modifier">
    <pre>
      {{ JSON.stringify(formValues, null, 2)}}
    </pre>
  </div>
  <div id="name">
    <label for="name" id="name">Name</label>
    <input type="text" id="name" v-model.trim.lazy="formValues.name" />
  </div>
  <div id="pro">
    <label for="profile" id="pro">Profile Summary</label>
    <input type="text" id="name" v-model="message" v-on:keyup.enter="sendMessage" />
  </div>
  <div id="btn">
    <button id="sub" @click.once="clicked">Submit</button>
  </div>
  <div id="link">
    
    <a href="https://vuejs.org/" v-on:click.prevent="showDialog" target="_blank">Or here!</a>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      formValues: {
        name: '',
        
      },
    }
    
  },
  methods: {
    sendMessage(){
      console.log(this.message);
      
    },
    clicked(){
      alert('okay');
    },
    
    showDialog(){
      alert('"Hello World!"');
    }
  },
}
  // methods: {
	// 	pressedEnter: function() {
	// 		alert("You pressed the Enter key!");
	// 	}
	// }
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
#name{
  margin-bottom: 10px;
  padding: 10px;
}
#pro{
  margin-bottom: 10px;
  padding: 10px;
}
#link{
  margin-bottom: 10px;
}
#btn{
  margin-bottom: 10px;
}
</style>
