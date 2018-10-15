<template>
    <div>
        <h2>post by ID</h2>

        <form>
            <div class="form-control">
                <label for="selectID">Select Post ID: </label>
                <select v-on:change="getPostID" name="selectID">
                    <option v-bind:disabled="postID !== ''" checked>Select an option</option>
                    <option v-for="post in posts" v-bind:key="post._id" :value="post._id">{{post._id}}</option>
                </select>
               <div class="postData" v-show="postID !==''">
                   <h2>{{post.name}}</h2>
                   <div>
                       <p>ID: {{post._id}}</p>
                       <p>{{post.description}}</p>
                    </div>
               </div>
            </div>
        </form>
    </div>
</template>


<script>
import gql from "graphql-tag";

export default {
    
  data(){
    return{
      postID: "",
      post:""
    }
  },
   apollo:{
    
    posts: gql`query {
      posts{
        _id
      }
    }`,
    post:{
        query: gql`query GetPost($id: String!){
            post(_id: $id){
                name
                description
                _id
            }
      }`,
     variables(){
        let x= this;
            return{
                id: x.postID
            }
    },
    skip () {
        let y= this;
        return !y.postID
      },
    }
  },
  methods:{
    getPostID:function(e){   
       this.postID = e.target.value;
       console.log(e.target.value)
    } 
    
  }
}



</script>

<style scoped>

  .post {
    -webkit-box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    -moz-box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    box-shadow: 0px 10px 31px -10px rgba(0,0,0,0.75);
    padding: 10px;
  }

  .postData {
    padding-bottom: 20px;      
  }

  select{
      padding: 10px;
      border-radius: 5px;
      color: rgb(255, 77, 130);
      font-size: 1.2rem;
  }
</style>

