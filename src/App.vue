<template>
  <div id="app">
    <UserCard v-bind:user="user"/>
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
  data(){
    return{
      user: {
        avatar_link: '/src/assets/70.jpg',
        full_name: 'Иванов Иван Иванович',
        nick_name: 'zxcromashka',
        adress: 'Москва, Юбилейная 50',
        email: 'hotrabbit@example.com',
        phone_number: '+7 (999) 999-01-01',
      }
    }
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
