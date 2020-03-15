<template>
  <div class="article-list">
    <div v-for="(item,index) in articleList" :key="index" class="article-main">
         <div style="height:20px;"></div>
        <div class="article-title">{{item.title}}</div>
         <div style="height:10px;"></div>
        <div class="article-remark">
            <img src="~static/日历.png" class="article-remark-img"/>&nbsp;{{item.date}}
            &nbsp;&nbsp;&nbsp;&nbsp;
            <img src="~static/分类.png" class="article-remark-img"/>&nbsp;{{item.category}}
        </div>
        <div style="height:10px;"></div>
        <div class="article-content">
            {{item.content}}
        </div>
        <div class="open-all"> <nuxt-link :to="{name:'article_detail-id',params:{id:1}}">查看全文&nbsp;></nuxt-link ></div>
        <div style="height:10px;"></div>
    </div>
  </div>
</template>

<script>
export default {
    props:['articleList'],
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
.article-list{
    
}
.article-main{
    background: white;
    border-radius: 10px;
    padding: 10px;
    margin:10px;
    margin-top:20px;
}
.article-title{
    /* text-align: center; */
    font-size: 20px;
    color: rgb(44, 91, 179);
    line-height: 40px;
}
.article-remark{
    font-size: 14px;
    line-height: 18px;
    /* height: 30px; */
    color: gray;
}
.article-remark-img{
    width: 15px;
}
.article-content{
    line-height: 24px;
}
.open-all {
    text-align: right;
    color:rgb(55, 98, 158);
    cursor: pointer;
}
.open-all a{
color:rgb(55, 98, 158);
}
</style>