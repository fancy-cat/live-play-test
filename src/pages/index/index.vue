<template>
  <div class="header">
    <div class="page__bd">
      <div class="weui-tab">
        <div class="weui-navbar" size="mini">
          <block v-for="(item,index) in tabs" :key="index">
            <div
              :id="index"
              :class="['weui-navbar__item', activeIndex === index ? 'weui-bar__item_on' : '']"
              @click="tabClick"
            >
              <div class="weui-navbar__title">{{item}}</div>
            </div>
          </block>
        </div>
        <div class="weui-tab__panel">
          <div v-for="(play,index) in playerList" :key="index" class="flex-wrap" @click="toPlaydetail">
            <div class="flex-item-l">
              <img src="../../../static/images/play.png"/>
            </div>
            <div class="flex-item-r">
              <h3>直播标题{{play.id}}</h3>
              <div>快进来看看吧哈哈哈哈哈哈哈哈哈哈哈。。。</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      tabs: ['热门', '关注', '广场'],
      activeIndex: 0,
      playerList: [{id: 1}, {id: 2}, {id: 3}, {id: 4}, {id: 5}, {id: 6}, {id: 7}]
    }
  },
  methods: {
    toPlaydetail () {
      console.log(111)
      wx.navigateTo({url: '/pages/play/main'})
    },
    tabClick (e) {
      console.log(e)
      this.activeIndex = Number(e.currentTarget.id)
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
  .weui-tab {
    position: fixed;
    top: 0;
    width: 100%;
  }
  .weui-navbar {
    background: #fff;
  }
  .page__bd {
    height: 100%;
  }
  .page__bd {
    padding-bottom: 0;
  }
  .weui-navbar__title {
    display: block;
  }
  .weui-tab__content {
    padding-top: 30px;
    text-align: center;
  }
  .flex-wrap {
    display: flex;
  }
  .flex-item-l {
    flex: 2;
  }
  .flex-item-l img {
    width: 100%;
    height: 100px;
  }
  .flex-item-r {
    flex: 2;
    padding-left: 10px;
  }
  .flex-item-r h3 {
    font-size: 20px;
    font-weight: 700;
  }
</style>
