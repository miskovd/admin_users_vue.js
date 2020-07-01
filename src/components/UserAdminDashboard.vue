<template>
  <div class="user-admin-dashboard">
    <Search></Search>
    <Table></Table>
  </div>
</template>

<script>
let users = require('../assets/users.json');

import Search from './Search'
import Table from './Table'


export default {
  name: 'HelloWorld',
  components: {
    Table, Search
  },
  data: () => ({
    users: users
  }),
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .user-admin-dashboard{

  }
</style>
