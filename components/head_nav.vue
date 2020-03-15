<template>
    <div class="home-head">
      <div class="home-nav">
        <div class="pen-name">✎逐梦鼠</div>
        <div class="page-remark">林丰浩的个人站点</div>
        <div class="page-nav">
          <div class="nav" v-for="(item,index) in navList" :key="index" :class="active==index+1?'active':''">
            <img :src="item.img" class="nav-img"/>
            <nuxt-link :to="{name:item.url.name,params:{id:123,title:'新页面'}}">{{item.name}}</nuxt-link >
            </div>
          <div class="nav" style="margin-right:150px;"></div>
          <div style="clear:both"></div>
        </div>
        <div style="clear:both"></div>
      </div>
      
    </div>

</template>

<script>

export default {
  props:['navList','active'],
  data() {
    return {
        img:require("../static/家.png"),
    }
  }
}
</script>

<style>
.home-box{
  /* background-color: rgb(255, 251, 240);
  height: 1000px; */
}
.home-head{
  background-color: rgb(242, 219, 210);
  /* padding-top:10px; */
  line-height: 60px;
  height: 60px;
}
.home-nav{
  width: 1200px;
  margin: auto;
  /* font-size: 25px; */
}
.pen-name{
  font-size:24px; 
  color: rgb(44, 91, 179);
  float: left;
}
.page-remark{
  float: left;
  font-size: 15px;
  color:gray;
  margin-left: 10px;
  line-height: 40px;
  margin-top:15px;
}
.page-nav{
  float:right;
}
.nav{
  float: left;
  margin-right: 50px;
  font-size: 16px;
  line-height: 50px;
  margin-top:10px;
}
.nav a{
  cursor: pointer;
}
.nav a:hover{
  color: rgb(44, 91, 179);
  font-weight: 700
}
.active a{
  color: rgb(44, 91, 179);
  font-weight: 700;
}
.nav-img{
  width: 16px;
  height: 16px;
  margin-right: 5px;
  float: left;
  margin-top:16px;
}
</style>

