<template>
  <div id="app">
    <Video/>
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Video from "./components/layout/Video";


export default {
  name: "app",
  components: {
    Header,
    Video
  }
}
</script>


<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  
}
</style>
