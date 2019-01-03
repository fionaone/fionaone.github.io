<template>
  <div :class="['cover',{'mini':rightShow}]">
    <div class="inwarp">
      <h1>Fiona</h1>
      <transition name="fade">
        <P>一个人静静坐在电脑面前写代码是武林高手闭关修炼的感觉</P>
      </transition>
      <div class="btn-group">
        <x-button round plain @click="toggleIndex()">
          <span v-if="!rightShow">OPEN 〖  我的信息  〗</span>
          <span v-else>CLOSE 〖  我的信息  〗</span>
        </x-button>
        <x-button round plain @click="go('https://healen.github.io/xui')">
          〖  X-UI   〗
        </x-button>

        <x-button round plain>
          〖  BLOG   〗
        </x-button>

      </div>
      <div class="icongroup">
        <i class="ico ico-weixin" @click="showQrcode(true)"></i>
        <i class="ico ico-qq" @click="goBlank('https://wpa.qq.com/msgrd?v=3&uin=789559633&site=qq&menu=yes')"></i>
        <i class="ico ico-github" @click="goBlank('https://github.com/fiona')"></i>
      </div>
    </div>

    <x-popup v-model="show" position="center"  :overlay="true"  :close-on-click-overlay="false" @click-overlay="showQrcode(false)">
      <img :src="require('./img/qrcode.png')" @click="showQrcode(false)" class="qrcode">
      <p>扫一扫，加我微信</p>
    </x-popup>



  </div>
</template>

<script>
  import {mapState} from 'vuex'
  export default {
    name: "cover",
    computed:{
      ...mapState([
        'rightShow'
      ])
    },
    data(){
      return {
        show:false
      }
    },
    methods:{
      go(url){
        window.location.href=url
      },
      toggleIndex(){
        if(this.rightShow){
          this.$router.push('/')
        }else {
          this.$router.push('/about')
        }
      },
      goBlank(url){
        window.open(url)
      },
      showQrcode(bool){
        this.show = bool
      }
    }
  }
</script>

<style scoped lang="less">
  @import "./index";

</style>