<template>
  <div id="app">
    <el-container>
      <el-header>
        <HeaderElement/>
      </el-header>
    </el-container>
    <el-container>
      <el-aside>
        <AsideElement/>
      </el-aside>
      <el-main>
        <MainElement/>
      </el-main>
    </el-container>
  </div>
</template>

<script>
import HeaderElement from './components/HeaderElement.vue';
import AsideElement from './components/AsideElement.vue';
import MainElement from './components/MainElement.vue'; 

export default {
  name: 'App',
  
  components: {
    HeaderElement:HeaderElement,
    AsideElement:AsideElement,
    MainElement:MainElement
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3384d5;
}
</style>
