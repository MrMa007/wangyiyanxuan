<template>
  <div class="re_exploreRcmds">
    <header>严选甄品</header>
    <div class="list" >
      <a  v-if="zhenpin.zhenOne"
        class="mainPosItem" href=""
      :style="`background-image: url(${zhenpin.zhenOne.picUrl})`">
        <div class="topicTag">{{zhenpin.zhenOne.nickname}}</div>
        <div class="content">
          <div >
            <div class="title">{{zhenpin.zhenOne.title}}</div>
            <div class="price">{{zhenpin.zhenOne.priceInfo}}元起</div>
          </div>
          <div class="subTitle">{{zhenpin.zhenOne.subtitle}}</div>
        </div>
      </a>
      <a v-if="zhenpin.zhenpins"
        class="minorPosItem" href="" v-for="(item,index) in zhenpin.zhenpins" :key="index">
        <div class="topicInfo">
        <div class="author">
          <img :src="item.avatar" alt="">
          {{item.nickname}}</div>
        <div class="title">{{item.title}}</div>
        <div class="line2">{{item.subtitle}}</div>
      </div>
        <div class="imgContainer "
             :style="`background-image: url(${item.picUrl})`">
          <div>{{item.typeName}}</div>
        </div>
      </a>
    </div>

  </div>
</template>
 <script>
   import {mapState} from 'vuex'
  export default {
    mounted(){
      this.$store.dispatch('getZhenpin')
    },
    computed:{
      ...mapState(['zhenpin'])
    },

    components: {}
  }
</script>

<style scoped lang="less">
  .re_exploreRcmds{
    width: 100%;
    background-color: white;
    margin-bottom: 20px;
    header{
      width: 690px;
      margin: auto;
      height: 120px;
      line-height: 120px;
      font-size: 32px;
      text-align: center;
      color: #333;
    }
    .list{
      .mainPosItem{
        display: block;
        margin: auto;
        border: 1px solid #d9d9d9;
        width: 690px;
        height: 574px;
        margin-bottom: 20px;
        background-size: 688px 386px;
        background-repeat: no-repeat;
        .topicTag{
          width: 130px;
          height: 32px;
          border-radius: 16px;
          background-color: white;
          margin-top: 20px;
          margin-left: 20px;
          font-size: 24px;
          color:#333 ;
          text-align: center;
          line-height: 32px;
        }
        .content{
          /*width: 688px;*/
          padding: 370px 19.5px;
          margin: auto;
          .title{
            text-align: left;
            display: inline-block;
            line-height: 90px;
            font-size: 32px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            color: #333;
          }
          .price{
            margin-top: 20px;
            float: right;
            text-align: right;
            display: inline-block;
            font-size: 32px;
            color: #333;
          }
          .subTitle{

            color: #7f7f7f;
            font-size: 28px;
            text-overflow: ellipsis;
            white-space: nowrap;
            overflow: hidden;
          }
        }
      }
      .minorPosItem{
        margin: auto;
        display: block;
        width: 690px;
        height: 274px;
        margin-bottom: 20px;
        border: 1px solid #d9d9d9;
        position: relative;
        .topicInfo{
          float: left;
          margin-left: 20px;
          width: 408px;
          height: 272px;
          .author{
            margin-top: 45px;
            img{
              height: 46px;
              width: 46px;
              border-radius: 50%;
              vertical-align: middle;
            }
            vertical-align: middle;
            font-size: 20px;
            color: #333;
          }
          .title{
            width: 328px;
            overflow: hidden;
            display: inline-block;
            white-space: nowrap;
            font-size: 32px;
            line-height: 90px;
            color: #333;
            text-overflow: ellipsis;

          }
          .line2{

            width: 358px;
            height: 70px;


            display:-webkit-box;
            -webkit-line-clamp:2;
            -webkit-box-orient:vertical;
            overflow: hidden;
            text-overflow: ellipsis;
            font-size: 24px;
            color: #7f7f7f;
            line-height: 1.5;
          }
        }
        .imgContainer{
          width: 280px;
          height: 272px;
          position: absolute;
          top: 0;
          right: 0;
          background-size: 280px 272px;
          div{
            display: inline-block;
            height: 36px;
            line-height: 36px;
            border-radius: 20px;
            background-color: white;
            margin-top: 20px;
            margin-left: 20px;
            padding: 0 5px;
            font-size: 22px;
            color: #666;
          }

        }
      }
    }
  }

</style>
