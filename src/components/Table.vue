<template>
  <div class="table">
    <table>
      <thead>
        <tr>
          <th 
            v-for="(item, index) in tableOrder" 
            :key="index" 
            >{{item}}
          </th>
        </tr>
        <tr v-for="(row, key) in computedData" 
        :key="key">
          <td v-for="(param, param_key) in tableOrder" :key="param_key">

            <span v-if="param != 'picture'">{{row[param]}}</span>
            <img :src="row[param]" v-else-if="param == 'picture'" />

          </td>
          <!-- <td>{{user.name}}</td>
          <td><img :src="user.picture" alt=""></td>
          <td>{{user.email}}</td> -->
        </tr>
      </thead>
    </table>
  </div>
  
</template>

<script>
export default {
    name: 'Table',
    props: ['data', 'searchTerm'],
    data: () => ({
      tableOrder: ['name','picture','email']
    }),
    computed: {
      computedData () {
        return this.data.filter(
          row => 
            row.name.includes(this.searchTerm) ||
            row.email.includes(this.searchTerm)
        )
      }
    }
}
</script>

<style scoped></style>