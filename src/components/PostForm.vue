<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Name"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Description"
    />
    <my-button 
    class="btn" 
    @click="createPost"
    >Create</my-button>
  </form>
</template>

<script>

export default {
  
  data() {
    return {
      post: {
        title: 'eee',
        body: 'rrr',
      },
    }
    
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
      
    }
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 10px;
}

form {
  display: flex;
  flex-direction: column;
}

.btn {
  align-self: flex-end;
  margin-top: 15px;
}
</style>