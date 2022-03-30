<template>
  <div class="app">
    <form class="form">
      <input class='input' type="text" placeholder="Название">
      <input class='input' type="text" placeholder="Описание">
      <button @click="createPost" class='btn'>Добавить пост</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong> {{post.title}}</div>
      <div><strong>Описание:</strong> {{post.body}}</div>
    </div>

  </div>
</template>

<script>
  export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascipt', body: 'описание JS'},
        {id: 2, title: 'Pyton', body: 'описание Pyton'},
        {id: 3, title: 'Ruby', body: 'описание Ruby'},
        {id: 4, title: 'C++', body: 'описание C++'}
      ]
    }
  },

  methods: {
    
  }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .app {
    padding: 20px;
  }

  .post {
    padding: 5px;
    margin-top: 15px;
    border: 2px solid teal;
  }

  .form {
    display: flex;
    flex-direction: column;

  }

  .input {
    width: 100%;
    border:1px solid teal;
    pad: 10px 15px;
    margin-top: 15px;
  }

  .btn {
    margin-top: 15px;
align-self: flex-end;
padding: 10px;
background: #fff;
color:teal;
border:1px solid teal;
  }

</style>
