<template>
  <div id="app">
    <div id="nav">
      <router-view/>
    </div>    
  </div>
</template>

<style lang="scss">
*{

  font-family: 'Comfortaa', cursive;

}

  #app {

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-image: url('assets/space2_1.png');
  
  min-width: 400px;
  min-height: 700px;
  
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

a {
  font-weight: bold;
  color: #b5e3ff;

  &:hover {
    color: #f7f7f7;;
    font-size: 1.2em;
    text-decoration: none;
  }
}
</style>
