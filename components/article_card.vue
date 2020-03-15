<template>
  <div class="article-card-box">
    <div class="article-title">学习笔记</div>
    <div class="article-card-main">
        <nuxt-link :to="{name:'article_detail-id',params:{id:1}}">div重叠时的显示顺序</nuxt-link >
    </div>
     <div style="height:10px;"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    };
  },
  methods: {
    aaa() {}
  },
  created() {
  }
};
</script>

<style scoped>
 .article-card-box{
     background: white;
     margin-top:20px;
     margin:15px 15px;
     border-radius: 10px;
 }
 .article-title{
     text-align: center;
     line-height: 40px;
     margin: 0 10px;
     border-bottom: 1px gray solid;
 }
 .article-card-main{
     margin-left:10px;
     line-height: 30px;
     cursor: pointer;
 }
 .article-card-main a:hover{
     color:rgb(135,206,235)
 }
</style>