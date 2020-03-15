<template>
  <div class="home-box">
      <head_nav :navList="navList" active="1"></head_nav>
     <home_main :articleList="articleList" :detail="true" :articleMsg="articleMsg"></home_main>
  </div>
</template>

<script>
import head_nav from '@/components/head_nav'
import home_main from '@/components/home_main'
export default {
  components:{
    head_nav,home_main
  },
  async asyncData({route}) {
      let navList = [
          {name:'首页',img:require("../../static/家.png"),url:{name:"index"}},
          {name:'技能',img:require("../../static/技能标签.png"),url:{name:"skill"}},
          {name:'项目',img:require("../../static/项目.png"),url:{name:"myWorks"}},
          {name:'工作经历',img:require("../../static/工作.png"),url:{name:"workHistory"}},
      ]
      let articleId = route.params.id
      let articleList = [
        {title:"div重叠时的显示顺序",date:"2020-2-25",category:"css",content:"当两个div重叠在一起的时候，样式会显示得非常奇怪，这个时候需要设置position将其设置为可重叠状态，如果需要指定哪个div在上面，可以通过设置z-index属性设置层级优先级。"},]
      let articleMsg = articleList[articleId-1]
      return {navList,articleList,articleMsg}
  },
  data() {
    return {

    }
  },
  mounted(){
      console.log("1111",this.articleMsg);
      
  },
  head(){
      return{
          title:"笔记详情 | "+this.articleMsg.title,
          meta:[
              {hid:'description',name:'个人站点-笔记详情',content:"笔记详情："+this.articleMsg.title}
          ]
      }
  }
}
</script>

<style>
.home-box{
  /* background-color: rgb(255, 251, 240);
  height: 1000px; */
}

</style>

