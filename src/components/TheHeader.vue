<template>
  <div>
    <nav>
      <router-link to="/">Home</router-link> 
      <router-link to="/about">About</router-link> 
      <router-link to="/weather">Weather</router-link> 
      <router-link to="/">News</router-link>
    </nav>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
nav {
    display: flex;
    background-color: whitesmoke;
    border: 3px solid gray;
    border-radius: 5px;
    padding: 5px;
    flex-direction: row;
    justify-content: space-evenly;
    align-content: center;
    
}

div{
    padding-right: 10%;
    padding-left: 10%;
}
</style>