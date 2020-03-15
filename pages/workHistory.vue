<template>
  <div class="home-box">
    <head_nav :navList="navList" active="4"></head_nav>
    <div class="home-main">
      <div class="article-list-box">
        <div class="myworks-box" v-for="(item,index) in workList" :key="index">
            <div style="height:20px"></div>
            <div class="myworks-title">公司：{{item.name}}</div>
            <div class="myworks-time">工作时间：{{item.time}}</div>
            <div class="myworks-position">职位：{{item.position}}</div>
            <div class="myworks-skill">公司常用技能：<font color="red">{{item.skill}}</font></div>
            <div class="myworks-remark">工作内容：{{item.remark}}</div>
            <div style="height:20px"></div>
        </div>
      </div>
      <div class="message-box">
        <name_card></name_card>
        <article_card></article_card>
        <note_card></note_card>
      </div>
      <div style="clear:both"></div>
    </div>
  </div>
</template>

<script>
import head_nav from '@/components/head_nav'
import name_card from "@/components/name_card";
import note_card from "@/components/note_card";
import article_card from "@/components/article_card";
export default {
  components: {
    name_card,
    article_card,
    note_card,
    head_nav
  },
  data() {
    return {};
  },
  async asyncData() {
      let navList = [
          {name:'首页',img:require("../static/家.png"),url:{name:"index"}},
          {name:'技能',img:require("../static/技能标签.png"),url:{name:"skill"}},
          {name:'项目',img:require("../static/项目.png"),url:{name:"myWorks"}},
          {name:'工作经历',img:require("../static/工作.png"),url:{name:"workHistory"}},
      ]
      let workList = [
          {name:'深圳安邦网络科技有限公司',time:"2017/9-2019/10",position:"web前端开发工程师",skill:"web原生态+vue+element+mpvue+小程序",
          remark:"公司主要是替客户开发响应式网页，小程序之类的，我主要是根据组长所布置的任务进行网页 的开发，包括前端界面的开发，功能组件，以及项目测试优化"},
          
      ]
       return {navList,workList}
  },
  methods: {
    aaa() {}
  },
   head(){
      return{
          title:"个人站点 | 工作经历",
          meta:[
              {hid:'description',name:'雏草逐梦',content:"林丰浩的个人站点--工作经历"}
          ]
      }
  }
 
};
</script>

<style scoped>
.home-main{
  width: 1200px;
  margin: auto;
  height: 100%;
  /* border: 1px solid red; */
}
.article-list-box{
  float: left;
  width: 65%;
  /* border: 1px solid red; */
  margin-right: 1%;
  /* background: white; */
  margin-top:20px;
  /* border-radius: 10px;; */
  /* background: white; */
}
.myworks-box{
    padding:0 20px;
    background: white;
    border-radius: 10px;
    margin:20px 0;
    line-height: 30px;
}
.myworks-title{

}
</style>