<template>
  <div id="app">
    <div id="nav">
            <img src=".\assets\invit.png" width="30px" height="25px" >
            <router-link to="/">jackApi v1.9.18.4</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
* {
  margin: 0%;
  padding: 0%;
  
}

#app {
  font-family: 'Press Start 2P', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FfF;
  
}

#nav {
  height: 30PX;
  background-color: #696969;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

img {
  position: absolute;
  top: 2.5px;
  left: 5px;
}

#nav a.router-link-exact-active {
  color:  #000000;
  position: absolute;
  top: 5px;
  left: 40PX;
  text-decoration: none;
}
</style>
