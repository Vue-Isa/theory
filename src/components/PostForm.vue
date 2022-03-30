<template>
  <form class="form" @submit.prevent>
    <h2>Создание поста</h2>
    <my-input v-model="post.title" type="text" placeholder="Название" />
    <my-input v-model="post.body" type="text" placeholder="Описание" />
    <my-button style="align-self: flex-end; margin: 15px 0" @click="createPost"
      >Добавить пост</my-button
    >
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
        id: null,
      },
    };
  },

  methods: {
    createPost() {
      this.post.id = Date.now;
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}
</style>
