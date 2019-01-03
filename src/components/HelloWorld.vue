<template>
  <div class="hello">
    <el-table
        :data="tableData3"
        style="width: 100%">
      <el-table-column type="expand">
        <template slot-scope="props">
          <component :is="'test'"></component>
        </template>
      </el-table-column>
      <el-table-column
          label="Date"
          prop="date">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import Vue from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    tableData3: [
      {
        date: '2016-05-03',
        name: 'Tom',
        state: 'California',
        city: 'Los Angeles',
        address: 'No. 189, Grove St, Los Angeles',
        zip: 'CA 90036'
      }
    ]
  }),
  created() {
    Vue.component('test', () => import(`@/components/test`))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
