<template>
<div>
  <h2>Posts component</h2>
  <div class="postsContainer">
    <div class="post" v-for="post in posts" v-bind:key="post._id">
      <h2>{{post.name}}</h2>
      <span>{{post._id}}</span>
      <hr />
      <div>
        {{post.description}}
      </div>
    </div>
  </div>
  </div>
</template>


<script>
import gql from "graphql-tag";

export default {
  data(){
    return{
      // posts: ""
    }
  },
  apollo:{
  posts: gql`query {
      posts{
        _id
        name
        description
      }
    }`
  },
  
}



</script>

<style scoped>

  .postsContainer {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    padding: 30px;
   }

  .post {
    -webkit-box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    -moz-box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    padding: 10px;
  }
  

</style>
