<template>
  <div class="form-todo form-group">
    <p>
      <input
        type="text"
        placeholder="Nome"
        name="author"
        class="form-control"
        v-model="name"
      />
    </p>
    <p>
      <textarea
        name="message"
        placeholder="Comentário"
        class="form-control"
        v-model="message"
      ></textarea>
    </p>
    <button
      class="btn btn-primary"
      type="button"
      v-on:click="addComment"
      :disabled="!message.trim()"
    >
      Comentar
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      message: ""
    };
  },
  methods: {
    // Adiciona um comentário à lista
    addComment() {
      if (!this.message.trim()) {
        return;
      }

      // Define "Anonymous" como padrão se o nome estiver vazio
      const commenterName = this.name.trim() || "Anonymous";

      // Emite um evento com os dados do comentário
      this.$emit("new-comment", {
        id: Date.now(), // ID único
        name: commenterName, // Nome ou "Anonymous"
        message: this.message.trim()
      });

      // Limpa os campos de entrada
      this.name = "";
      this.message = "";
    }
  }
};
</script>

<style>
.form-todo {
  margin: 20px 0;
}
.form-todo input,
.form-todo textarea {
  width: 100%;
  margin-bottom: 10px;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
button {
  display: block;
  width: 100%;
  padding: 10px;
  background-color:#007bff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold !important;
  
}
button:disabled {
  background-color: #aaa;
  cursor: not-allowed;
}
</style>
