<template>
  <div>
    <el-table
      ref="elTable"
      :data="data"
      v-bind="$attrs"
      v-on="$listeners"
    >
      <one-column
        v-for="(column, index) in columns"
        :key="index"
        :column="column"
      />
    </el-table>
  </div>
</template>
<script>
import OneColumn from './one-column'

export default {
  name: 'OneTable',
  components: { OneColumn },
  props: {
    columns: Array,
    data: Array
  },
  data () {
    return {
      value: null
    }
  },
  methods: {
    clearSelection () {
      this.$refs.elTable.clearSelection()
    },
    toggleRowSelection (row, selected) {
      this.$refs.elTable.toggleRowSelection(row, selected)
    },
    toggleAllSelection () {
      this.$refs.elTable.toggleAllSelection()
    },
    toggleRowExpansion (row, expanded) {
      this.$refs.elTable.toggleRowExpansion(row, expanded)
    },
    setCurrentRow (row) {
      this.$refs.elTable.setCurrentRow(row)
    },
    clearSort () {
      this.$refs.elTable.clearSort()
    },
    clearFilter (columnKey) {
      this.$refs.elTable.clearFilter(columnKey)
    },
    doLayout () {
      this.$refs.elTable.doLayout()
    },
    sort (prop, order) {
      this.$refs.elTable.sort(prop, order)
    }
  }
}
</script>
