<template>
  <UserCard v-bind:img="img" v-bind:nickname="nickname" v-bind:firstname="firstname" 
  v-bind:lastname="lastname" v-bind:address="address"
  v-bind:mail="mail" v-bind:phone="phone">
  </UserCard>
  <button @click="getUserData">Обновить</button>
</template>

<script>
import UserCard from './components/UserCard.vue'

export default {
  name: 'App',
  components: {
    UserCard
  },
  data(){
  return {
    img: "../assets/img/70.jpg",
    nickname: 'romashka',
    firstname: 'Иванов Иван',
    lastname: 'Иванович',
    address: "Москва, Юбилейная 50",
    mail: "coldrabbit48@example.com",
    phone: "+7-495-266-57-34"
  }
  },
  methods: {
    getUserData(){
      this.axios.get('https://randomuser.me/api/')
        .then((response) => {
          console.log(response.data)
          this.img = response.data['results'][0]['picture']['large']
          this.nickname = response.data['results'][0]['id']['name']
          this.firstname = response.data['results'][0]['name']['first']
          this.lastname = response.data['results'][0]['name']['last']
          this.address = response.data['results'][0]['location']['street']['name']
          this.mail = response.data['results'][0]['email']
          this.phone = response.data['results'][0]['phone']
        })
    }
  }
}
</script>

<style>

</style>
