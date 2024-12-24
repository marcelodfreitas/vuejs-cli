<template>
  <div class="container">
    <h1>Comentários</h1>
    <hr />
    <TodoForm v-on:new-comment="newComment"></TodoForm>
    <br />
    <div class="list-group">
      <p v-if="comments.length <= 0">Sem Comentários...</p>
      <div class="list-group-item" v-for="(comment, index) in computedComments" :key="comment.id">
        <span class="comment_author">
          Autor: <strong>{{ comment.name }}</strong>
        </span>
        <p>{{ comment.message }}</p>
        <a 
          href="#" 
          title="Excluir" 
          aria-label="Excluir comentário" 
          v-on:click.prevent="delComment(index)"
        >
          Excluir
        </a>
      </div>
    </div>
    <hr />
  </div>
</template>

<script>
import TodoForm from './TodoForm.vue';

export default {
  components: {
    TodoForm
  },
  data() {
    return {
      comments: JSON.parse(localStorage.getItem('comments')) || []  // Recupera os comentários do localStorage
    };
  },
  methods: {
    newComment(comment) {
      this.comments.push(comment);
      this.saveComments();  // Salva os comentários no localStorage após adicionar um novo
    },
    delComment(index) {
      this.comments.splice(index, 1);
      this.saveComments();  // Salva os comentários no localStorage após excluir um comentário
    },
    saveComments() {
      localStorage.setItem('comments', JSON.stringify(this.comments));  // Salva os comentários no localStorage
    }
  },
  computed: {
    computedComments() {
      return this.comments;
    }
  },
  watch: {
    comments(val) {
      console.log("Comentários atualizados:", val);
    }
  }
};
</script>

<style>
.comment_author {
  font-weight: bold;
  color: #333;
}
.list-group-item {
  margin-bottom: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
a {
  color: red;
  cursor: pointer;
  text-decoration: none;
}
</style>
