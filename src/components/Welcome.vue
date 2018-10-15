<template>
  <div class="welcome">
    <header>
      <h1>VueGraphQL Client</h1>
        <p>Welcome to the VueJs + Apollo Client app.</p>
    </header>
   
 
   <img src="./../assets/36790 [Converted].svg" />
  </div>
</template>

<script>

</script>

<style scoped>
.welcome{
   position: relative;
   height: 400px;
   overflow: hidden;
}
header {
  width: 50%;
}

  header h1{
    font-size: 4rem;
    line-height: 4rem;
    text-transform: uppercase;
    margin: 0;
    padding-top: 100px;
  }

  header p{
    font-size: 1.3rem;
    line-height: 1.3rem;
    width: 80%;
    margin: 0;
  }
  img{
    width: 80%;
    position: absolute;
    top: 0;
    right: 0;
  }
</style>

