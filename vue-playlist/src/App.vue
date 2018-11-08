<template>
  <div id="app">
    <!-- <app-header v-on:titleChanged="updateTitle($event)" :title="title"></app-header>
    <users :users="users"></users>
    <app-footer :title="title"></app-footer> -->
    <ul>
      <li><router-link to="/">home</router-link></li>
      <li><router-link to="/helloworld">hello</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
// import Users from "./components/Users"
// import Header from "./components/Header"
// import Footer from "./components/Footer"

export default {
  name: 'App',
  data(){
    return {
      // users:[
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false},
      //   {name:"henry",position:"web开发",show:false}
      // ],
      // title:"传递的是一个值"
    }
  },
  // components: {
  //   Users,
  //   "app-header":Header,
  //   "app-footer":Footer,
  // },
  created(){
    //fetch跨域
    fetch("/apis/test/testToken.php",{
      method:"post",
      body:JSON.stringify({username:"crj",password:"123123"})
    })
    .then(result => {
      // console.log(result);
      return result.json()
    })
    .then(data => {
      console.log(data);
    })
  },
  methods:{
    // updateTitle(title){
    //   this.title = title
    // }
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
