<template>
  <div id="app">
    <UserCard :user="user"/>
    <button @click="parceUserData()">get new user</button>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import UserCard from './components/UserCard.vue'

export default {
  name: 'App',
  components: {
    UserCard
  }, 
  methods: {
    parceUserData(){
      this.axios.get("https://randomuser.me/api/")
      .then((responce) =>
      {
        let user = responce.data.results[0];
        console.log(user);
        this.user.email = user.email;
        this.user.full_name = user.name.first + " " + user.name.last;
        this.user.nick_name = user.login.username;
        this.user.phone_number = user.phone;
        this.user.adress = 
        user.location.country + ", " + user.location.city + ", " + user.location.street.name + " " + user.location.street.number;
        this.user.avatar_link = user.picture.large;
      })
    }
  },
  data(){
    return{
      user: {
        avatar_link: '../assets/70.jpg',
        full_name: 'Иванов Иван Иванович',
        nick_name: 'zxcromashka',
        adress: 'Москва, Юбилейная 50',
        email: 'hotrabbit@example.com',
        phone_number: '+7 (999) 999-01-01',
      }
    }
  },
  mounted(){
    this.parceUserData()
  }
 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
