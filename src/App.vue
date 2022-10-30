<template>
  <div class="app">
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
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
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
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
</style>

