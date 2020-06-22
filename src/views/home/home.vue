<!-- home -->
<template>
  <div class="home_box">
    <header class="home_header">
      <div class="home_title">游戏久</div>
      <van-icon size="20" name="https://b.yzcdn.cn/vant/icon-demo-1126.png" />
    </header>
  </div>
</template>

<script>
// 请求接口
import { getUserInfo } from '@/api/user.js'
import { mapGetters } from 'vuex'
export default {
  data() {
    return {}
  },
  computed: {
    ...mapGetters(['userName'])
  },
  mounted() {
    this.initData()
  },
  methods: {
    // 请求数据案例
    initData() {
      // 请求接口数据，仅作为展示，需要配置src->config下环境文件
      //   const params = { user: 'sunnie' }
      //   getUserInfo(params)
      //     .then((res) => {
      //         console.log(res,'res')
      //     })
      //     .catch(() => { })
    },
    // Action 通过 store.dispatch 方法触发
    doDispatch() {
      this.$store.dispatch('setUserName', '真乖，赶紧关注公众号，组织都在等你~')
    }
  }
}
</script>
<style lang="scss" scoped>
.home_box {
  height: 100%;
  .home_header {
    height: 40px;
    background-color: aqua;
    display: flex;
    justify-content: center;
    position: relative;
    .home_title {
      line-height: 40px;
      font-size: 16px;
      text-align: center;
    }
    /deep/.van-icon {
      position: absolute;
      right: 15px;
      height: 0.26667rem;
      top: 10px;
      width: 0.26667rem;
      cursor: pointer;
    }
  }
}
</style>
