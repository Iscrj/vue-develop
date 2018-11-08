<template>
  <div id="home">
    <app-header v-on:titleChanged="updateTitle($event)" :title="title"></app-header>
    <users :users="users"></users>
    <app-footer :title="title"></app-footer>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import Users from "./Users"
import Header from "./Header"
import Footer from "./Footer"

export default {
  name: 'home',
  data(){
    return {
      users:[
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false},
        // {name:"henry",position:"web开发",show:false}
      ],
      title:"传递的是一个值"
    }
  },
  components: {
    Users,
    "app-header":Header,
    "app-footer":Footer,
  },
  created(){
    this.$http.get("http://jsonplaceholder.typicode.com/users")
    .then((data) => {
      // console.log(data)
      this.users = data.body;
    });
  },
  methods:{
    updateTitle(title){
      this.title = title
    }
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
