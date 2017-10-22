<template>
  <transition name="move">
        <div v-show="isShow" class="food" ref="food">
     <div class="food-content">
       <div class="image-header">
         <img :src="food.image">
         <div class="back" @click="show(false)">
           <i class="icon-arrow_lift"></i>
         </div>
       </div>

       <div class="content">
         <h1 class="title">{{food.name}}</h1>
         <div class="detail">
           <span class="sell-count">月售{{food.sellCount}}份</span>
           <span class="reting">haopinglv{{food.rating}}%</span>
         </div>
         <div class="price">
           <span class="now">￥{{food.price}}</span>
           <span class="old" v-show="food.oldPrice">￥{{food.oldPrice}}</span>
         </div>
        <!-- <div class="cartcontrol-wrapper">

        </div> -->
       </div>

       <split></split>

       <div class="info">
         <h1 class="title">商品信息</h1>
         <p class="text">{{food.info}}</p>
       </div>

       <split></split>

       <div class="rating">
         <h1 class="title">商品评价</h1>
       </div>
     </div>
        </div>
  </transition>
</template>
<script>
import Vue from 'vue'
import split from '../split/split.vue'
import BScroll from 'better-scroll'
export default {
  props:{
    food:Object,
  },
  data(){
    return{
      isShow:false,
    }
  },
  methods:{
    show(isShow){
     this.isShow = !this.isShow
    }
  },
  component:{
    split
  }

}
</script>
<style lang="stylus" ref="stylesheet/stylus">
  @import "../../common/stylus/mixins.styl"
</style>


