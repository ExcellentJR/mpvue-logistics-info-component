<template>
  <div class="total-wrap">
    <div class="logistics-title">物流跟踪</div>
    <block v-for="(item, index) in tracesData" :key="index">
      <trackNode :is-first="index===tracesData.length-1" :is-newest="index===0" :is-main-node="item.isMainNode" :node-data="item"></trackNode>
    </block>
  </div>
</template>

<script>
import trackNode from '@/components/trackNode'

export default {
  data () {
    return {
      tracesData: [
        {
          acceptStation: '包裹已被吴亦发同学签收', // 节点描述
          acceptTime: '2019-10-24 15: 27: 27',
          createTime: '2019-10-24 15: 27: 16',
          id: 63,
          logisId: 35,
          logisNo: 'sf000999888', // 物流订单号
          platformCode: 'SF', // 平台信息
          status: 'COMPLETE', // 节点状态
          phone: '', // 电话
          statusName: '已签收', // 节点标题
          isMainNode: true // 是否主节点，主节点前方展示icon
        },
        {
          acceptStation: '由派送员蔡小坤同志配送，电话：',
          acceptTime: '2019-10-24 15: 26: 46',
          createTime: '2019-10-24 15: 26: 41',
          id: 62,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'DELIVERING',
          phone: '16677778888',
          statusName: '运输中',
          isMainNode: true
        },
        {
          acceptStation: '已到XXX小区快递点',
          acceptTime: '2019-10-24 15: 26: 26',
          createTime: '2019-10-24 15: 26: 41',
          id: 62,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'DELIVERING',
          phone: '',
          statusName: '运输中',
          isMainNode: false
        },
        {
          acceptStation: '已到海宁集散中心',
          acceptTime: '2019-10-24 15: 26: 26',
          createTime: '2019-10-24 15: 26: 18',
          id: 61,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'DELIVERING',
          phone: '',
          statusName: '运输中',
          isMainNode: false
        },
        {
          acceptStation: '已到杭州集散中心',
          acceptTime: '2019-10-24 15: 25: 25',
          createTime: '2019-10-24 15: 26: 07',
          id: 60,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'DELIVERING',
          phone: '',
          statusName: '运输中',
          isMainNode: false
        },
        {
          acceptStation: '包裹已到达余杭区集散中心',
          acceptTime: '2019-10-24 15: 25: 25',
          createTime: '2019-10-24 15: 25: 54',
          id: 59,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'DELIVERING',
          phone: '',
          statusName: '运输中',
          isMainNode: false
        },
        {
          acceptStation: '快递员已上门取件',
          acceptTime: '2019-10-24 15: 25: 25',
          createTime: '2019-10-24 15: 25: 17',
          status: 'WATTING_DELIVER',
          phone: '',
          statusName: '已揽收',
          isMainNode: true
        },
        {
          acceptStation: '已发货',
          acceptTime: '2019-10-24 15: 24: 24',
          createTime: '2019-10-24 15: 25: 00',
          id: 57,
          logisId: 35,
          logisNo: 'sf000999888',
          platformCode: 'SF',
          status: 'WATTING_DELIVER',
          phone: '',
          statusName: '已揽收',
          isMainNode: false
        },
        {
          acceptStation: '订单支付成功，等待商家发货',
          acceptTime: '2019-10-24 15: 24: 14',
          createTime: '2019-10-24 15: 22: 30',
          status: 'PAYED',
          statusName: '已支付',
          isMainNode: true
        },
        {
          acceptStation: '订单提交成功',
          acceptTime: '2019-10-24 15: 23: 23',
          createTime: '2019-10-24 15: 22: 00',
          status: 'WATTING_PAY',
          statusName: '已下单',
          isMainNode: true
        }
      ]
    }
  },
  components: {
    trackNode
  },
  created () {
    // let app = getApp()
  }
}
</script>

<style lang="less" scoped>
.total-wrap {
  width: 100vw;
  height: auto;
  box-sizing: border-box;
  padding: 20rpx 40rpx 200rpx;
  .logistics-title {
    height: 72rpx;
    box-sizing: border-box;
    padding: 36rpx 0 8rpx;
    line-height: 28rpx;
    color: #4B4B4B;
    font-size: 26rpx;
    font-family: 'PingFangSC-Medium';
    text-align: left;
  }
}
</style>
