<template>
  <UserCard v-bind:nickname="nickname" v-bind:firstname="firstname" 
  v-bind:lastname="lastname" v-bind:address="address"
  v-bind:mail="mail" v-bind:phone="phone">
  </UserCard>
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
    nickname: 'romashka',
    firstname: 'Иванов Иван',
    lastname: 'Иванович',
    address: "Москва, Юбилейная 50",
    mail: "coldrabbit48@example.com",
    phone: "+7-495-266-57-34"
  }
  }
}
</script>

<style>

</style>
