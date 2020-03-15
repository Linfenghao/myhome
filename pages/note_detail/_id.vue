<template>
  <div class="home-box">
      <head_nav :navList="navList" active="1"></head_nav>
     <home_main :articleList="articleList" :noteMsg="noteMsg" :note="true"></home_main>
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
      let noteId = route.params.id
      let articleList = [
        {id:1,title:"div重叠时的显示顺序",date:"2020-2-25",category:"css",content:"当两个div重叠在一起的时候，样式会显示得非常奇怪，这个时候需要设置position将其设置为可重叠状态，如果需要指定哪个div在上面，可以通过设置z-index属性设置层级优先级。"},]
      let noteList = [
          {id:1,title:"建站",content:"在2020年2月25号初建个人站点，虽然很多功能暂未完善，但也算是迈出了一步，后续希望将此个人站点修改为个人博客",date:"2020-2-25"}
      ]
      let noteMsg = noteList[noteId-1]
      return {navList,articleList,noteMsg }
  },
  data() {
    return {

    }
  },
  mounted(){
      console.log(this.routeList);
      
  },
  head(){
      return{
          title:"笔记详情 | "+this.noteMsg.title,
          meta:[
              {hid:'description',name:'个人站点-笔记详情',content:"笔记详情："+this.noteMsg.title}
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

