<template>
  <div class="app">
    <h1>Post Page</h1>
    <my-button
      class="btn__create"
      @click="showDialog"
    >Create Post</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost"/>
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue'
import PostList from '@/components/PostList.vue'

export default {
  components: {
    PostForm,
    PostList,
  },

  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Post about JawaScript",
          body: "JavaScript is universal programing langveg",
        },
        {
          id: 2,
          title: "Post about JawaScript2",
          body: "JavaScript is universal programing langveg2",
        },
        {
          id: 3,
          title: "Post about JawaScript3",
          body: "JavaScript is universal programing langveg3",
        },
      ],
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogVisible = false
    },
    removePost(post) {
      this.posts = this.posts.filter(item => item.id !== post.id)

    },
    showDialog() {
      this.dialogVisible = true
    },
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 10px;
}

.btn__create {
  margin: 10px 0;
}
</style>

