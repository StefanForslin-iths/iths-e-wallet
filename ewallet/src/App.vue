<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/AddCard">addCard</router-link>
    </div> -->
    <router-view/>
  </div>
</template>
<style>
* {
  box-sizing: border-box;
  font-family: 'Times New Roman', Times, serif;
}
body {
  margin: 0;
  background-color: aqua;
}
#app {
  width: 24rem;
  height: 100vh;
  margin: 0 auto;
  padding: 1rem;
}
.col-2 {
  grid-column: auto / span 2;
}
.row-2 {
    grid-row: auto / span 2;
}
.addbutton {
    display: grid;
    place-items: center;
    height: 100px;
    width: 100%;
    margin: 2rem 0;
    border: .125rem dotted rgb(201, 111, 111);
    border-radius: 0px;
    background-color: #fff;
    font-size: 1.2rem;
    font-weight: 600;
    text-transform: uppercase;
}
.addbutton:hover {
    background-color: rgb(15, 78, 150);
    color: #fff;
}
</style>
