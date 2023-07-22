<script>
import axios from 'axios'
import CardComponent from '../components/Cards.vue'
export default {
  components: {
    CardComponent
  },
  data() {
    return {
      usersList: []
    }
  },
  mounted() {
    //fetch data from the api upon mounting of the component
    axios
      .get('https://jsonplaceholder.typicode.com/users')
      .then((response) => (this.usersList = response.data))
  }
}
</script>

<template>
  <div class="container">
    <h1>Users</h1>
    <div class="users-list">
      <CardComponent
        v-for="user in usersList"
        :imageUrl="`https://robohash.org/${user.id}?set=2&size=180x180`"
        :title="user.name"
        :options="false"
        :key="user.id"
      />
    </div>
    <hr />
  </div>
</template>

<style lang="scss">
.users-list {
  /* width: 85vw; */
  margin: 40px auto;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 10px;
}
hr {
  margin: 30px;
  border-color: #828282;
}
</style>
