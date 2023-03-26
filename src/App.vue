<template>
  <header class="movie-app"> 
    <router-link to="/">
      <h1><span>Vue</span>Movie</h1>
    </router-link>
  </header>
  <main>
    <router-view/>
  </main> 
</template>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Fira+Sans:wght@100;300;400;500;600;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', serif;

  &::selection {
    background: transparentize(#42B883, $amount: .5);
  }
}

body {
  background-color: #27496D;
  box-sizing: border-box;
}

a {
  text-decoration: none;
}

header {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 16px;
  background-color: #142850;
  box-shadow: 0px 0px 6px rgba(29, 27, 27, 0.2);
  

  h1 {
    color: #FFF;
    font-size: 28px;

    span {
      color: #42B883;
    }
  }
  .movie-app {
    max-width: 375px;
    margin: 0 auto;
    z-index: 21;
  }
  

}
</style>
