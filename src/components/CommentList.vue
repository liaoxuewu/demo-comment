<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="comments.length === 0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <CommentItem v-for="(comment, index) in comments" :comment="comment"
      :key="index" :comment-delete="commentDelete" :index="index"></CommentItem>
    </ul>
  </div>
</template>
<script>
  import CommentItem from './CommentItem.vue';
  export default {
    //声明接收哪些属性
    props:['comments','commentDelete'],
    components:{
      CommentItem
    }
  }
</script>
<style>
  .reply {
    margin-top: 0px;
  }
</style>
