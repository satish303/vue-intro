<template>
<div class="btn-group" role="group" aria-label="Basic example">
  <button type="button" class="btn btn-primary">Left</button>
  <button type="button" class="btn btn-primary">Middle</button>
  <button type="button" class="btn btn-primary">Right</button>
</div>
<div class="btn-group" role="group" aria-label="Basic mixed styles example">
  <button type="button" class="btn btn-danger">Left</button>
  <button type="button" class="btn btn-warning">Middle</button>
  <button type="button" class="btn btn-success">Right</button>
  
</div >
<div className="cardInput">
<div class="card" style="width: 18rem;">
  <img src="https://images.unsplash.com/photo-1622434641406-a158123450f9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHdhdGNofGVufDB8fDB8fA%3D%3D&w=1000&q=80" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <h1>$99</h1>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
<div className="card" style="width: 18rem;">
  <img src="https://images.unsplash.com/photo-1622434641406-a158123450f9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHdhdGNofGVufDB8fDB8fA%3D%3D&w=1000&q=80" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <h1>$99</h1>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
<div class="card" style="width: 18rem;">
  <img src="https://images.unsplash.com/photo-1622434641406-a158123450f9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHdhdGNofGVufDB8fDB8fA%3D%3D&w=1000&q=80" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <h1>$59</h1>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
<div class="card" style="width: 18rem;">
  <img src="https://images.pexels.com/photos/190819/pexels-photo-190819.jpeg?cs=srgb&dl=pexels-fernando-arcos-190819.jpg&fm=jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
   
   <h1>{{formData.user}}</h1>
  <h1>{{formData.pass}}</h1>
   
   <button className="buy" @click="get">Buy</button>
  </div>
</div>
</div>

<button @click="get"> get data</button>
<div v-for="name in array" :key="name">
  <h1>{{name.body}}</h1>
 
</div>
<HelloWorld/>
</template>

<script>
import axios from 'axios'
import HelloWorld from "./components/HelloWorld"
export default {

  data(){
    return{
      array:[],
      formData:{
      user:"$99",
      pass:"5555"
      }
    }
  },
  name: 'App',
methods:{
  async get(){
    // fetch("https://jsonplaceholder.typicode.com/posts").then(res => res.json()).then(data => this.array = data )
   let response= await axios.post("http://localhost:3333/empdata", this.formData);
   this.array= response.data
   
  }
},
  components:{
 HelloWorld
  },
}
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
.cardInput{
  display: flex;
  justify-content:space-around;
}
img{
  height: 400px;
}
.card{
  border-radius: 10px!important
}
.buy{
  background-color:rgb(177, 177, 218)
}
</style>
