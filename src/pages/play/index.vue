<template>
  <div class="main-wrap">
    <div class="play-wrap">
      <live-player class="live-player" bindfullscreenchange="screenChange"></live-player>
      <div class="user-info">
        <span class="item">观看人数：777</span>
        <span class="item header-img">
          <img src="../../../static/images/play.png" alt="">
        </span>
        <button size="mini" class="item btn" @click="screenChange">关注</button>
      </div>
    </div>
    <div>123</div>
  </div>
</template>
<script>
export default {
  data () {

  },
  methods: {
    screenChange (e) {
      console.log(e)
    }
  }
}
</script>
<style scoped>
.main-wrap {
  width: 100%;
}
.play-wrap {
  position: fixed;
  top: 50;
  width: 100%;
}
.play-wrap .full-btn {
  position: absolute;
  top: 20px;
}
.live-player {
  width: 100%;
  height: 300px;
}
.user-info {
  position: absolute;
  top: 20px;
  right:0;
  color: #fff;
}
.item {
  display: inline-block;
  vertical-align: middle;
  margin-left: 5px;
}
.header-img {
  border: 1px solid #fff;
  border-radius: 50%;
  overflow: hidden;
  width: 30px;
  height: 30px;
}
.user-info .btn {
  padding: 1px 5px;
}

</style>
