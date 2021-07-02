
<script>
export default {
  name: 'OneColumn',
  props: {
    column: Object
  },
  render (h) {
    const { column } = this
    return (
      <el-table-column
        {...{ props: column }}
        {...{
          scopedSlots: {
            default: column.render
          }
        }}
      >
      </el-table-column>
    )
  }
}
</script>
