<template>
  <div id="app">
    <cnode-head></cnode-head>
    <router-view name="main"></router-view>
    <router-view name="side" ref="child"></router-view>
  </div>
</template>

<script>
  import cnodeHead from './components/cnodeHead.vue';
  export default {
    name: 'app',
    data () {
      return {
        authorName: ''
      }
    },
    components:{
      cnodeHead
    },
    watch:{
      authorName(val){
        this.$refs.child.name = val;
      }
    }
  }
</script>

<style lang="scss">
  html{
    font-size: 14px;
  }
  body{
    background-color: #e1e1e1;
    margin: 0;
    padding: 0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
