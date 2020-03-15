<template>
  <div class="home-box">
    <head_nav :navList="navList" active="3"></head_nav>
    <div class="home-main">
      <div class="article-list-box">
        <div class="myworks-box" v-for="(item,index) in worksList" :key="index">
            <div style="height:15px"></div>
            <div class="myworks-title">{{item.name}}</div>
            <div class="myworks-time">项目开发时间：{{item.time}}</div>
            <div class="myworks-skill">项目所用前端技术：<font color="red">{{item.skill}}</font></div>
            <div class="mywork-remark">项目描述：{{item.remark}}</div>
            <div style="height:10px"></div>
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
      let worksList = [
          {name:'个人站点',time:"2020/2-2020/3",skill:"nuxt+echarts",remark:"该项目因为考虑后续可以要做成类似博客站点，所以使用nuxt框架进行搭建，服务端渲染，方便SEO，目前只是比较简单的网页，笔记模块需要后续进行优化"},
          {name:'唐球',time:"2019/6-2019/10",skill:"mpvue+微信小程序+有赞组件库",remark:"唐球是一种新型的类似高尔夫的运动，这个小程序主要用于用户报名赛事，赛事数据保存查看，场 馆数据保存查看，以及用户比赛数据的保存和查看，该项目包括小程序用户界面，以及后台管理数据 pc 端页 面,小程序可以在微信中搜索唐球查看"},
          {name:'案件管理系统',time:"2019/5-2019/6",skill:"vue+element+TinyMCE富文本",remark:"这个项目主要是用于管理律师案件数据的，包括案件基本数据，附件列表，进展列表。这个项目 关键的地方是要进行权限设计，有两种管理员身份，普通会员，以及超级管理员，超级管理员可以查看所有案 件包括查看所有消息会员，而普通会员只能看到和他自身有关系的消息以及案件"},
          {name:'龙庭空调主页',time:"2019/3-2019/5",skill:"nuxt+element",remark:"该项目需要支持SEO，所以要使用nuxt框架进行服务端渲染，空调主页主要包括首页，产品，案列，空调维保几个模块,网址:http://www.szltkt.cn/"},
          
      ]
       return {navList,worksList}
  },
  methods: {
    aaa() {}
  },
  head(){
      return{
          title:"个人站点 | 我的项目",
          meta:[
              {hid:'description',name:'雏草逐梦',content:"林丰浩的个人站点--我的项目"}
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
}
.myworks-title{
    text-align: center;
    font-weight: 700;
    font-size: 22px;
    line-height: 35px;
}
.myworks-time,.myworks-skill,.mywork-remark{
    line-height:30px;
}
</style>