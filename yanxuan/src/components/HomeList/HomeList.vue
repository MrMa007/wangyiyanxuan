<template>
  <div class="home_list">
    <div class="banner">
      <img :src="cateList[index].bannerUrl" alt="">
    </div>
    <div class="indexFloor" >
        <h3>{{cateList[index].name}}</h3>
        <div class="goodGrid">
          <ul class="list">
            <li v-for="(good,index) in cateList[index].itemList" :key="index">
              <img :src="good.listPicUrl" alt="">
              <span class="desc">{{good.simpleDesc}}</span>
              <div>风格特惠</div>
              <span class="good">{{good.name}}</span>
              <span class="price">￥{{good.retailPrice}}</span>
            </li>
          </ul>

        </div>


    </div>

  </div>
</template>

<script>
  import {mapState} from 'vuex'

  export default {
    props:{
      index:Number
    },
    computed: {
      ...mapState(['cateList']),
    },


    components: {}
  }
</script>

<style scoped lang="less">
  .home_list{
    margin-bottom: 98px;
    .banner{
      width: 750px;
      height: 420px;
      margin-bottom: 20px;
      img{
        width: 750px;
        height: 420px;
      }
    }
    .indexFloor{
      width: 100%;
      background-color: white;
      margin-bottom: 20px;
      h3{
        width: 100%;
        height: 120px;
        text-align: center;
        font-size: 32px;
        line-height: 120px;
        color: #333;
      }
      .goodGrid{
        .list{
          background-color: white;
          li{

            display: inline-block;
            width: 345px;
            height: 595px;
            margin-left: 20px;
            img{
              width: 345px;
              height: 345px;
              background-color: #f4f4f4;
              vertical-align: middle;
            }
            .desc{
              display: inline-block;
              background-color: #F1ECE2;
              height: 69px;
              width: 345px;
              color: #9F8A60;
              font-size: 24px;
              line-height: 69px;
              white-space: nowrap;
              overflow: hidden;
              text-overflow: ellipsis;
            }
            div{
              margin: 20px 0 0 15px;
              width: 92px;
              height: 30px;
              background-color: #f48f18;
              border-radius: 2px;
              font-size: 20px;
              text-align: center;
              color: white;
              line-height: 30px;
            }
            .good{
              display: block;
              margin: 20px 0 0 15px;
              font-size: 28px;
              color: #333;
              white-space: nowrap;
              overflow: hidden;
              text-overflow: ellipsis;

            }
            .price{
              color: #b4282d;
              font-size: 32px;
              display: inline-block;
              margin: 10px 0 0 10px;
            }


          }
          /*a{*/
            /*background-color: #f4f4f4;*/
            /*display: inline-block;*/
            /*width: 345px;*/
            /*height: 414px;*/
            /*margin-right: 12px;*/
            /*text-align: center;*/
            /*span{*/
              /*width: 100%;*/
              /*font-size: 32px;*/
              /*color: #333;*/
              /*display: block;*/
              /*margin-top: 150px;*/

            /*}*/
            /*img{*/
              /*margin: auto;*/
              /*display: block;*/
              /*margin-top: 50px;*/
            /*}*/

          /*}*/
        }
      }
    }

  }

</style>
