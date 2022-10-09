<template>
  <div id="App">
    <home/>
  </div>
</template>

<script>
import home from './pages/home.vue' 

export default {
  name: 'App',
  components:{
    home,
  }
}
</script>

<style>
@import url('./style/reset.css');
@import url('https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbU4ycFdZd3djSm1YUzZ6MG8yZ3c0cG03UEZsZ3xBQ3Jtc0ttdUJwMFN6UEp1TXNfTkNvS1V4eC1maVUybVc0UUZhMDBpTjJJaXVtZC1PU2J5MUtPTjFCMk5RYTBUMUg3bTkyb2ctYUI4MHlfamFUWlFEQUxQc09UU1FxcDVuOVN3TUo1azYwci1VcF9yUmZTTFc1QQ&q=https%3A%2F%2Ffonts.googleapis.com%2Fcss2%3Ffamily%3DRoboto%3Awght%40300%3B400%3B700%26display%3Dswap&v=pY2DwnKJdTs');
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  padding: 20px;
}
</style>
