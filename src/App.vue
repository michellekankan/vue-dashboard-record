<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  created(){
    const api = `${process.env.APIPATH}/api/${process.env.CUSTOMPATH}/products`
    console.log(process.env.APIPATH, process.env.CUSTOMPATH)
    // API 伺服器路徑
    // 所申請的 APIPath

    this.$http.get(api).then((response) => {
      console.log(response.data)
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
