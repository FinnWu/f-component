<template>
  <div id="app">
    <one-table :columns="columns" :data="data" />
  </div>
</template>

<script>
import OneTable from '@/components/OneTable/index'
export default {
  name: 'app',
  components: {
    OneTable
  },
  data () {
    return {
      columns: [
        {
          prop: 'name',
          label: '姓名'
        },
        {
          prop: 'age',
          label: '年龄',
          render ({ row }) {
            return row.age + 1
          }
        }
      ],
      data: [
        {
          name: 'finnwu',
          age: 24,
          address: '盘古电梯'
        }
      ]
    }
  }
}
</script>

<style>

</style>
