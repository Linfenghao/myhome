<template>
    <div class="name_card_box">
      <div style="height:20px;"></div>
      <div class="head-portrait-box">
          <img src="~static/头像.jpg" class="head-portrait-img"/>
      </div>
      <div style="height:10px;"></div>
      <div class="remark-box">
          <div style="color:rgb(96,189,255);font-size: 16px;"> 逐梦鼠 </div>
          <div>专注WEB前端开发</div>
      </div>
      <div class="identifying-box">
          <div class="card-box" :style="{background:'#FFC0CB',color:'#FF1493',border:'1px solid #FF1493'}">vue</div>
          <div class="card-box" :style="{background:'#87CEEB',color:'#0000FF',border:'1px solid #0000FF'}">react</div>
          <div class="card-box" :style="{background:'#90EE90',color:'#458B74',border:'1px solid #458B74'}">小程序</div>
          <div class="card-box" :style="{background:'#F5DEB3',color:'#CD853F',border:'1px solid #CD853F'}">node</div>
          <div class="card-box" :style="{background:'#32CD32',color:'#228B22',border:'1px solid #228B22'}">java</div>
          <div class="card-box" :style="{background:'#EEDC82',color:'#CD9B1D',border:'1px solid #CD9B1D'}">mongodb</div>
          <div style="clear:both"></div>
      </div>
      <div class="contact-box">
          <div class="contact-ramark">—— —— 社交 —— —— </div>
          <div style="height:10px;"></div>
          <div class="contact-img">
              
          <div class="contact-img-box">
              <div class="img-remark" style="width:150px">qq:654029036</div>
              <div style="height:10px;" class="hed"></div>
              <div><img src="~static/qq.png"/></div>
          </div>
          <div class="contact-img-box">
              <div class="img-remark" style="width:150px">wx:654029036</div>
              <div style="height:10px;" class="hed"></div>
              <div><img src="~static/微信.png"/></div>
          </div>
          <div class="contact-img-box">
              <a href="https://github.com/Linfenghao" target="_blank">
              <div class="img-remark">github:https://github.com/Linfenghao</div>
              <div style="height:10px;" class="hed"></div>
              <div><img src="~static/github.png"/></div>
              </a>
          </div>
          <div class="contact-img-box">
              <a href="http://www.linfenghao.cn" target="_blank">
              <div class="img-remark">个人站点:www.linfenghao.cn</div>
              <div style="height:10px;" class="hed"></div>
              <div><img src="~static/个人.png"/></div>
              </a>
          </div>
          <div style="clear:both"></div>
          </div>
      </div>

    </div>
</template>

<script>

export default {
  props:['navList','active'],
  data() {
    return {

    }
  }
}
</script>

<style>
.name_card_box{
    background: white;
    height: 380px;
    margin:15px 15px;
    border-radius: 10px;
}
.head-portrait-box{
    width: 90px;
    margin: auto;
    border-radius: 50%;
    overflow: hidden;
    height: 90px;
}
.head-portrait-img{
    width: 90px;
    height: 90px;
}
.remark-box{
    text-align: center;
    line-height: 35px;
    font-size: 14px;
    color:gray ;
}
.card-box{
    float: left;
    width: 28%;
    text-align: center;
    border-radius: 5px;
    margin:10px 0px;
    margin-left: 10px;
}

.contact-ramark{
    position: relative;
    text-align: center;
    color:gray;
    line-height: 30px;
}
.contact-img{
    padding-left:18px;
}
.contact-img-box{
    float: left;
    width: 30px;
    height: 30px;
    background: gray;
    padding: 5px;
    border-radius: 50%;
    margin-left:25px;
}

.contact-img-box div img{
    width: 100%;
}
.img-remark{
    line-height: 30px;
    margin-right: -25px;
    margin-left: -80px;
    position: relative;
    display: none;
    margin-top: -40px;
    height: 30px;
    background-color: rgba(0, 0, 0, 0.5);
    font-weight: 700;
    text-align: center;
    color: white;
    width: 300px;
}
.contact-img-box:hover .img-remark{
    display: block;
}
.hed{
    display: none;
}
.contact-img-box:hover .hed{
    display: block;
}
</style>

