<template>
  <div class="about">
    <transition name="fade">

      <swiper :options="swiperOption" v-if="showbanner" ref="mySwiper" >
        <swiper-slide class="sliderbox slider1">
          <div class="cons">
            <img :src="require('../assets/img/fiona.png')" class="photo"/>
            <h2>要么做第一个，要么做最好的一个。</h2>
            <div class="line"></div>
            <p class="disa">赵淑英</p>
            <p class="disa">前端开发攻城狮一枚</p>
            <p class="disa">girl_fiona@126.com</p>
            <p class="disa">&nbsp;</p>
            <p class="disa">&nbsp;</p>
          </div>
        </swiper-slide>
        <swiper-slide class="sliderbox slider2">
          <div class="cons">
            <h1>关于我</h1>

            <ul class="status">
              <li>
                <div>
                  <i class="ico ico-status"></i>
                  状态／在职
                </div>
              </li>
              <li>
                <div>
                  <i class="ico ico-age"></i>
                   经验／9年
                </div>
              </li>
              <li>
                <div>
                  <i class="ico ico-address"></i>
                  住址／旧宫
                </div>
              </li>
              <li>
                <div>
                  <i class="ico ico-xueli"></i>
                  学历／本科
                </div>
              </li>
            </ul>
            <p class="dis1">九年互联网经验,六年半全职前端开发经验</p>
            <p class="dis1">具备 部署、架构、带队、管理、培训新人等能力</p>
            <p class="dis1">深谙自动化,模块化开发之道</p>
            <p class="dis1">高效的自学能力,具备独立分析解决问题能力</p>
            <p class="dis1">九年苦行，悟出前端 "道" 的本质</p>
          </div>

        </swiper-slide>
        <!--<swiper-slide class="sliderbox slider3">-->
          <!--<div class="cons">-->

            <!--<h1>技能栈</h1>-->

          <!--</div>-->
        <!--</swiper-slide>-->

        <!--<swiper-slide class="sliderbox slider4">-->
          <!--<div class="cons">-->

            <!--<h1>经历</h1>-->

          <!--</div>-->
        <!--</swiper-slide>-->

        <!--<swiper-slide class="sliderbox slider5">-->
          <!--<div class="cons">-->

            <!--<h1>作品集</h1>-->

          <!--</div>-->
        <!--</swiper-slide>-->

        <!--<swiper-slide class="sliderbox slider6">-->
          <!--<div class="cons">-->

            <!--<h1>联系我</h1>-->

          <!--</div>-->
        <!--</swiper-slide>-->
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>

    </transition>

    <div class="-arrow">
      <x-icon name="up"></x-icon>
    </div>

  </div>
</template>
<script>
  import "swiper/dist/css/swiper.css"
  export default {
    name: "About",
    data(){
      return {
        showbanner:false,
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          },
          autoplay: {
            delay: 5000, //自动切换的时间间隔，单位ms
            stopOnLastSlide: false, //当切换到最后一个slide时停止自动切换
            disableOnInteraction:true
          },
          effect: 'cube',
          grabCursor: true,
          cubeEffect: {
            shadow: true,
            slideShadows: true,
            shadowOffset: 20,
            shadowScale: 0.94,
          },
          direction: 'vertical',
          mousewheel : true,
          speed:500,
        }
      }
    },
    created(){
      setTimeout(()=>{
        this.showbanner= true
      },500)
    },
    destroyed(){
      this.showbanner= false
    }
  }
</script>
<style lang="less">
  @import "About";
</style>