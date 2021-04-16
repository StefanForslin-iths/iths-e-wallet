<template>
  <div id="app">
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
  background-color: rgb(180, 141, 141);
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
    border: .125rem dotted rgb(199, 196, 196);
    border-radius: 0px;
    background-color: #fff;
    font-size: 1.2rem;
    font-weight: 600;
    text-transform: lowercase;
}
.addbutton:hover {
    background-color: rgb(130, 153, 179);
    color: #fff;
}
</style>
