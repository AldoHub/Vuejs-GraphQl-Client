<template>
  <div id="app">
    <nav>
      <ul>
       <li><router-link to="/">Home</router-link></li>
       <li><router-link to="/posts">Posts</router-link></li>
       <li><router-link to="/post">PostByID</router-link></li>
      </ul>
    </nav>
    <router-view></router-view>
  </div>
</template>

<script>


export default {
 
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Poppins');
  
  body {
    background: #eee;
    font-family: poppins;
 }
 h2 {
    border-bottom: 2px solid rgb(98, 217, 253);
    text-transform: uppercase;
  }
  #app {
    width: 70%;
    margin: 0 auto;
   
   background: #fff;
    -webkit-box-shadow: 0px 10px 24px -6px rgba(0,0,0,0.75);
    -moz-box-shadow: 0px 10px 24px -6px rgba(0,0,0,0.75);
    box-shadow: 0px 10px 24px -6px rgba(0,0,0,0.75);
    display: grid;
    grid-template-columns: 1fr 10fr;
    grid-gap: 30px;
    
  }


  nav {
    margin: 0;
    padding: 0px;
    background: rgb(255, 77, 130);
  }
  nav ul {
    padding: 0;
    margin: 0;
  }
  nav ul li{
    list-style: none;
    display: inline-block;
    margin: 0px;
    border-bottom:1px solid #fff;
    width: 100%
  }
  nav ul li a {
    display: block;
    padding: 10px;
    color: #fff;
    text-align: center;
    font-weight: bold;
    text-decoration: none;
  }

  input, textarea {
    font-family: poppins;
  }
 


</style>
