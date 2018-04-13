<template>
  <div class="hello">
     <head-me></head-me>
     <div class="mid_w">
        <div class="menu_w">
        
           <ul>
             <li  v-on:mouseenter="_ballRoll()" v-on:mouseout="_ballOut()" v-for="item in menuLists">
               <div class="text">{{item.name}}</div>
               <div class="ball" ref="myBall">

               </div>
             </li>
          
           </ul>
        
        </div>
        <div class="con_w">
           <div class="title_w">
             <p>OUR SERVICE</p>
             <p>服务范围</p>
           </div>
           <div class="service_list">
              <div class="s_li01" v-for="item in cates">
                 <div class="sli_n">
                    <p class="design_img"><img :src="item.img" alt=""></p>
                    <div class="category">
                       <h2>{{item.textTitle}}</h2>
                       <p>{{item.chinaText}}</p>
                    </div>
                 </div>
              </div>
           </div>
          <div class="title_w">
             <p>CASES STUDY</p>
             <p>案例展示</p>
           </div>
           <div class="case_lists">
             <slider :pages="pages" :sliderinit="sliderinit">
                
             </slider>
           </div>
        </div>
     </div>
     <bootm-foor></bootm-foor>
  </div>
</template>

<script>
import slider from 'vue-concise-slider'// 引入slider组件
import HeadMe from "@/components/head/head";
import BootmFoor from "@/components/bottom/bottomFoor";
export default {
  components: {
      HeadMe,
      BootmFoor,
      slider
    },
  data () {
    return {
        //图片列表[arr]
        pages:[
          {
            title: 'slide1',
            style:{
             background: '#d3a3f9'
            }
          },
          {
           title: 'slide2',
           style:{
            background: '#f26e16'
            }
          },
          {
            title: 'slide3',
            style:{
              background:'#4bbfc3',
            },
          }
        ],
        //滑动配置[obj]
        sliderinit: {
          currentPage: 0,//当前页码
          thresholdDistance: 500,//滑动判定距离
          thresholdTime: 100,//滑动判定时间
          autoplay:4000,//自动滚动[ms]
          loop:true,//循环滚动
          direction:'horizontal',//方向设置，垂直滚动
          infinite:2,//无限滚动前后遍历数
          slidesToScroll:1,//每次滑动项数
          prevButton:'.swiper-button-prev',//上一张
          nextButton:'.swiper-button-next'//下一张
        },      
       cates: [
         {
           'img':require('./img/design_l.png'),
           'textTitle': 'DESIGN',
           'chinaText': '设计'
         },
         {
           'img': require('./img/develop.png'),
           'textTitle': 'DEVELOP',
           'chinaText': '开发'           
         },
         {
            'img': require('./img/solution.png'),
            'textTitle': 'SOLUTION',
            'chinaText': '方案'          
         },
         {
           'img':require('./img/operation.png'),
           'textTitle': 'OPERATION',
           'chinaText': '托管'          
         }         
      ],
      menuLists: [
         {'name':'移动App'},
         {'name':'企业网站'},
         {'name':'电商网站'},
         {'name':'响应式网站'},
         {'name':'软件开发'},
         {'name':'平面设计'},
         {'name':'ui设计'},
         {'name':'关于我们'},
      ],
      isA: false,
      isB: false
    }
  },
  methods: {
 
  }
}
</script>
<style scoped>
.mid_w {
  width: 1200px;
  height: 540px;
  margin: 0 auto;
}
.mid_w {
  display: flex;
}
.menu_w {
  width: 170px;
  height: 540px;
  background-color: #11f1c4;
}
.menu_w ul li {
  position: relative;
  height: 67px;
  line-height: 67px;
  text-indent: 20px;
  border-bottom: #fff solid 1px;
}
.text {
  position: absolute;
  left: 30px;
  top: 0px;
  z-index: 100;
}
.ball {
  position: absolute;
  display: none;
  background-color: yellow;
  display: block;
  top: 0px;
  left: 0px;
  width: 8px;
  height:64px;
  transition: width 1s;
  -moz-transition: width 1s; /* Firefox 4 */
  -webkit-transition: width 1s; /* Safari 和 Chrome */
  -o-transition: width 1s;
}
.ball:hover {
  width: 170px;
}
.con_w {
  flex: 1;
  height: 540px;
  background:url('./img/bg_img.png');
}
.title_w p {
  height: 30px;
  line-height:30px;
  font-size: 18px;
  text-align: center;
  color: #494949;
  font-weight: bold;
}
.title_w p:first-child {
  margin-top: 18px;
  font-size: 28px;
  color: #0d82a8;
  font-weight: bold;
}
.service_list {
  width: 1000px;
  height: 200px;
  margin: 0  auto;
  margin-top: 20px;
}
.service_list {
  display: flex;
}
.s_li01{
  flex: 1;
  text-align: center;
}

.sli_n {
  width: 200px;
  height: 199px;
  margin: 0 auto;
  background-color: red;
  border-radius: 5px;
  border:#ffffff solid 1px;
}
.s_li01:nth-child(1) .sli_n {
  background-color: #f65314;
}
.s_li01:nth-child(2) .sli_n {
  background-color: #26c7fc;
}
.s_li01:nth-child(3) .sli_n {
  background-color: #44b573;
}
.s_li01:nth-child(4) .sli_n {
  background-color: #5a3c82;
}
.design_img {
  margin-top: 30px;
}
.category h2 {
  margin-top: 10px;
  font-size: 25px;
  color: white;
  font-weight: bold;
}
.category p {
  font-size: 21px;
  margin-top: 5px;
  color: white;
}
.case_lists {
  width: 950px;
  margin: 0 auto;
  height: 140px;
  background-color: yellow;
}
</style>
