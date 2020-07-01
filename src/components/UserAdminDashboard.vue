<template>
  <div class="user-admin-dashboard">
    <Search v-model="searchTerm"></Search>
    <Table :data="users" :searchTerm="searchTerm"></Table>
  </div>
</template>

<script>
let users = require('../assets/users.json');

import Table from './Table'
import Search from './Search'



export default {
  name: 'HelloWorld',
  components: {
    Table, 
    Search
  },
  data: () => ({
    users: users,
    searchTerm: ''
  }),
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .user-admin-dashboard{

  }
</style>
