<template>
    <div class="comment-item" :class="{ selected: isSelected }" tabindex="0" @click="toggleSelect">
      <div class="comment-header">
        <strong class="username">{{ username }}</strong>
        <span class="comment-date">{{ formattedDate }}</span>
      </div>
      <p class="comment-body">{{ comment }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CommentItem',
    props: {
      username: {
        type: String,
        required: true
      },
      comment: {
        type: String,
        required: true
      },
      date: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        isSelected: false  // State untuk melacak apakah komentar dipilih
      }
    },
    computed: {
      formattedDate() {
        const dateObj = new Date(this.date);
        return dateObj.toLocaleString();
      }
    },
    methods: {
      toggleSelect() {
        this.isSelected = !this.isSelected;  // Toggle state saat komentar diklik
      }
    }
  }
  </script>
  
  <style scoped>
  .comment-item {
    background-color: #fff;
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 15px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    cursor: pointer;  /* Memberikan kursor tangan saat hover */
    transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease; /* Animasi transisi */
  }
  
  /* Efek saat item dipilih (menggunakan class 'selected') */
  .comment-item.selected {
    background-color: #d4edda; /* Warna hijau muda saat dipilih */
    transform: translateY(-5px); /* Memberikan efek timbul */
    box-shadow: 0 5px 15px rgba(0, 128, 0, 0.3); /* Efek bayangan lebih tegas */
  }
  
  /* Efek saat item di-hover atau focus */
  .comment-item:hover,
  .comment-item:focus {
    background-color: #f0f8ff; /* Highlight saat hover atau focus */
    outline: none; /* Menghapus outline default saat fokus */
  }
  
  .comment-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
  }
  
  .username {
    font-weight: bold;
    font-size: 1.1rem;
    color: #333;
  }
  
  .comment-date {
    font-size: 0.9rem;
    color: #888;
  }
  
  .comment-body {
    font-size: 1rem;
    color: #555;
    line-height: 1.5;
  }
  </style>
  