<template>
    <div class="comment-list">
      <h2>Comments</h2>
      <CommentItem
        v-for="(comment, index) in comments"
        :key="index"
        :username="comment.username"
        :comment="comment.comment"
        :date="comment.date"
      />
    </div>
  </template>
  
  <script>
  import CommentItem from './CommentItem.vue';
  
  export default {
    name: 'CommentList',
    components: {
      CommentItem
    },
    data() {
      return {
        comments: [
          {
            username: 'Haikal Muhammad',
            comment: 'The King Of All Role.',
            date: '2024-11-15T08:00:00Z'
          },
          {
            username: 'Faisal Zulmauludin',
            comment: 'Wow',
            date: '2024-11-14T10:30:00Z'
          },
          {
            username: 'Muhammad Maulidan',
            comment: 'The Biggers Of CEO.',
            date: '2024-11-13T14:15:00Z'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .comment-list {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f7f7f7;
    border-radius: 8px;
  }
  
  .comment-list h2 {
    font-size: 1.6rem;
    margin-bottom: 20px;
    color: #444;
    text-align: center;
  }
  </style>
  