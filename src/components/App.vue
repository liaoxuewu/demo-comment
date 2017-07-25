<template>
    <div>
      <header class="site-header jumbotron">
        <div class="container">
          <div class="row">
            <div class="col-xs-12">
              <h1>请发表对Vue的评论</h1>
            </div>
          </div>
        </div>
      </header>
      <div class="container">
      <CommentAdd :comment-add="commentAdd"></CommentAdd>
      <CommentList :comments="comments" :comment-delete="commentDelete"></CommentList>
      </div>
    </div>
</template>
<script>
  import CommentAdd from './CommentAdd.vue';
  import CommentList from './CommentList.vue';

  export default {
    data() {
      return{
        comments:[]
      }
    },
    created() {
      //模拟发送ajax请求，实现异步获取数据
      setTimeout(()=>{
        //获取数据
        const comments = [
          {
            username:'sj',
            content:'Vue很难'
          },
          {
            username:'lk',
            content:'Vue很简单'
          }
        ]
        //更新数据
        this.comments = comments
      },1000)
    },
    methods:{
      commentAdd(comment){
        this.comments.unshift(comment)
      },
      commentDelete(index){
        this.comments.splice(index,1);
      }
    },
    components:{
      CommentAdd,
      CommentList
    }
  }
</script>
<style>

</style>
