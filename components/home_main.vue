<template>
    <div class="home-main">
      <div class="article-list-box">
        <note_detail :noteMsg="noteMsg" v-if="note"></note_detail>
        <article_detail :articleMsg="articleMsg" v-else-if="detail"></article_detail>
        <article_list :articleList="articleList" v-else></article_list>
      </div>
      <div class="message-box">
        <name_card></name_card>
        <article_card></article_card>
        <note_card></note_card>
      </div>
      <div style="clear:both"></div>
    </div>
</template>

<script>
import article_list from '@/components/article_list'
import article_detail from '@/components/article_detail'
import name_card from '@/components/name_card'
import article_card from '@/components/article_card'
import note_card from '@/components/note_card'
import note_detail from '@/components/note_detail'
export default {
  components:{
    name_card,article_card,article_list,article_detail,note_card,note_detail
  },
  props:['navList','active','articleList','detail','articleMsg','note','noteMsg'],
  data() {
    return {

    }
  }
}
</script>

<style>
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
}
.message-box{
  float: left;
  width: 26%;
  /* border: 1px solid red; */
}
</style>

