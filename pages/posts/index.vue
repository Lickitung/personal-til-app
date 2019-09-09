<template>
    <div class="posts-page">
        <PostList :posts="loadedPosts"/>
        <!-- {{posts}} -->
    </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList
  },
  // data() {
  //   return {
  //     loadedPosts: [
  //       { id: '1', title: 'First Post', previewText: 'So it has come to my attention recen...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
  //       { id: '2', title: 'Second Post', previewText: 'Until recently I has assumed that it w...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
  //     ]
  //   }
  // },
  // created() {
  //   this.$store.dispatch('posts/setPosts', this.loadedPosts)
  // }
  fetch(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPosts: [
            { 
              id: '1', 
              title: 'First Post', 
              previewText: 'So it has come to my attention recen...', 
              thumbnail: 'https://source.unsplash.com/featured/?tech' 
            },
            { 
              id: '2', 
              title: 'Second Post', 
              previewText: 'Until recently I has assumed that it w...', 
              thumbnail: 'https://source.unsplash.com/featured/?tech' 
            },
          ]
        });
      }, 2000);
    })
    .then(data => {
      context.store.commit('posts/setPost', data.loadedPosts)
    })
    .catch(e => {
      context.error(new Error());
    })
  },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    }
  }
}
</script>

<style scoped>
.posts-page {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>