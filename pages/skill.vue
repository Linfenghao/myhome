<template>
  <div class="home-box">
    <head_nav :navList="navList" active="2"></head_nav>
    <div class="home-main">
      <div class="article-list-box">
        <div class="skill-table-box">
          <table border="1" cellspacing='0' cellpadding="1" class="skill-table">
                <tr v-for="(item,index) in skillList" :key="index">
                    <td class="table-left">{{item.skill}}</td>
                    <td class="table-right">{{item.remark}}</td>
                </tr>
        </table>
        </div>
        <div class="skill-img-remark">echarts技能图</div>
       <div id="img" class="skill-img" ></div>
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
import echarts from 'echarts';
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
      let skillList = [
            { skill: "技术", remark: "掌握程度" },
            { skill: "web原生态", remark: "大部分常用知识已经掌握，不常用的需看api" },
            { skill: "ES6", remark: "熟悉ES6的新特性，如模板字符串、解构赋值、扩展运算符" },
            { skill: "vue", remark: "熟悉vue的指令、router、vuex、组件化、生命周期...能够使用vue框架开发项目" },
            { skill: "nuxt", remark: "了解nuxt框架的基础知识，可以用nuxt实现服务端渲染" },
            { skill: "react", remark: "熟悉react的开发方式,了解redux、react-router，能够使用react框架开发项目" },
            { skill: "微信小程序", remark: "能够使用微信开发工具开发小程序,有用过mpvue用vue框架知识开发小程序" },
            { skill: "node", remark: "熟悉node的基础api,曾用过node开发接口" },
            { skill: "数据库", remark: "主要使用mongodb数据对接数据，了解mysql数据库" },
            { skill: "java", remark: "了解java的基础知识,但还不够熟悉，很难用于开发" },
            { skill: "git", remark: "之前公司使用git对项目进行版本管理，对svn也会使用" },
            { skill: "常用模块", remark: "element、moment、lodash、mock、echarts、TinyMCE" },
            
        ]
       return {navList,skillList}
  },
  methods: {
    aaa() {}
  },
  mounted() {
     var myChart = echarts.init(document.getElementById('img'));
        myChart.setOption({
           
            tooltip : {
                trigger: 'axis',
                axisPointer : {         
                    type : 'none'       
                }
            },
            xAxis: {
                type: 'value'
            },
            yAxis: {
                type: 'category',
                data:['java','node','数据库','小程序','react','vue','ES6','web原生态']
            },
            series: [
                {
                    name:"得分",
                    data: [40,50,50,70,70,90,80,80],
                    type: 'bar',
                    z:10,
                    itemStyle: {
                        normal: {
                            color: 'rgb(213,58,53)'
                        }
                    },
                },{
                name:"总分",
                data: [100,100,100,100,100,100,100,100],
                type: 'bar',
                barGap:'-100%',
                itemStyle: {
                    normal: {
                        color: 'rgb(230,230,230)'
                    }
                },
            },]
        })
        console.log("1111",myChart);
  },
   head(){
      return{
          title:"个人站点 | 我的技能",
          meta:[
              {hid:'description',name:'雏草逐梦',content:"林丰浩的个人站点--我的技能"}
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
  background: white;
  margin-top:20px;
  border-radius: 10px;;
  /* background: white; */
}
.message-box{
  float: left;
  width: 26%;
  /* border: 1px solid red; */
}
.skill-img-remark{
  margin-left: 20px;
  font-size: 20px;
  margin-top:10px;
  line-height: 30px;
  color: rgb(120,211,255);
}
.skill-img{
  margin-top:-40px;
  margin-left: 20px;;
    width: 100%;
    height: 450px;
}
.skill-table-box{
  margin: 30px 30px;
  /* margin-top:30px; */
}
.skill-table{
  border: 1px solid #00BFFF;
    border-collapse: collapse;
    width: 95%;
}
.table-left{
  line-height: 30px;
  font-weight: 700;
  text-align: center;
}
.table-right{
  text-align: center;
  line-height: 30px;
}
</style>