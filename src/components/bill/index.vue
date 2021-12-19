<template>
  <div>
    <h1>{{ msg }}</h1>
    <div>
    <el-table
    :data="tableData"
    style="width: 100%"
    :row-class-name="tableRowClassName">
    <el-table-column
      prop="ID"
      label="ID"
      width="50">
    </el-table-column>
    <el-table-column
      prop="amount"
      label="金额"
      width="100">
    </el-table-column>
    <el-table-column
      prop="time"
      label="时间"
      width="250">
    </el-table-column>
    <el-table-column
      prop="mode"
      label="支付方式"
      width="100">
    </el-table-column>
    <el-table-column
      prop="isOutput"
      label="收/支"
      width="180"
      :filters="[{ text: '支出', value: '1' }, { text: '收入', value: '1' }]"
      :filter-method="filterTag"
      filter-placement="bottom-end">
      <template slot-scope="scope">
        <el-tag
          :type="scope.row.label === '1' ? 'primary' : 'success'"
          disable-transitions>{{scope.row.label}}</el-tag>
      </template>
    </el-table-column>
    <el-table-column
      prop="label"
      label="标签"
      width="180"
      :filters="[{ text: 'food', value: '食物' }, { text: 'clothes', value: '衣服' }]"
      :filter-method="filterTag"
      filter-placement="bottom-end">
      <template slot-scope="scope">
        <el-tag
          :type="scope.row.tag === 'food' ? 'primary' : 'success'"
          disable-transitions>{{scope.row.label}}</el-tag>
      </template>
    </el-table-column>
    <el-table-column
      prop="remark"
      label="备注"
      width="280">
    </el-table-column>
        <el-table-column label="操作">
      <template slot-scope="scope">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'bill',
  data () {
    return {
      msg: '列表',
      tableData: [{
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }, {
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }, {
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }, {
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }, {
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }, {
        ID: 1,
        amount: 26.03,
        time: '2021/12/19 22:44:20',
        mode: 'wechat',
        isOutput: 1,
        label: 'food',
        remark: '备注'
      }]
    }
  },
  methods: {
    tableRowClassName ({row, rowIndex}) {
      if (rowIndex === 1) {
        return 'warning-row'
      } else if (rowIndex === 3) {
        return 'success-row'
      }
      return ''
    }
  }

}
</script>

<style scoped>
  .el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
</style>
