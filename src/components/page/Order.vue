<template>
  <el-table
    :data="tableData"
    border
    style="width: 100%">
    <el-table-column fixed prop="orderNo" label="订单号" width="150"></el-table-column>
    <el-table-column prop="userName" label="姓名" width="120"></el-table-column>
    <el-table-column prop="animalName" label="宠物名" width="120"></el-table-column>
    <el-table-column prop="phone" label="电话" width="120"></el-table-column>
    <el-table-column prop="card" label="会员卡" width="120"></el-table-column>
    <el-table-column prop="total" label="合计金额" width="120"></el-table-column>
    <el-table-column prop="discountMoney" label="优惠金额" width="120"></el-table-column>
    <el-table-column prop="balance" label="会员卡余额" width="120"></el-table-column>
    <el-table-column prop="realMoney" label="实付金额" width="120"></el-table-column>
    <el-table-column prop="refund" label="退款金额" width="120"></el-table-column>
    <el-table-column prop="orderTime" label="消费时间" width="120"></el-table-column>
    <el-table-column prop="detail" label="费用项目" width="120"></el-table-column>
    <el-table-column prop="number" label="数量" width="120"></el-table-column>
    <el-table-column prop="originalPrice" label="原价" width="120"></el-table-column>
    <el-table-column prop="salePrice" label="销售价" width="120"></el-table-column>
    <el-table-column prop="discountRate" label="折扣率" width="120"></el-table-column>
    <el-table-column prop="totalMoney" label="总计" width="120"></el-table-column>
    <el-table-column prop="cashier" label="收营员" width="120"></el-table-column>
    <el-table-column
      fixed="right"
      label="操作"
      width="100">
      <template slot-scope="scope">
        <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
        <el-button type="text" size="small">编辑</el-button>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
  export default {
    methods: {
      handleClick(row) {
        console.log(row);
      }
    },
    created() {
      this.getOrder()
    },

    data() {
      return {
        tableData: []
      }
    },
    methods: {
      getOrder() {
        this.$http.get('/api/user/getOrders', {
          a: 1
        })
          .then(res => {
            this.tableData = res.data
          })
      }
    }
  }
</script>