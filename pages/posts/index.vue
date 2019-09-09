<template>
    <div class="posts-page">
        <PostList :posts="loadedPosts"/>
    </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList
  },
  asyncData() {
      return new Promise(function(resolve, reject) {
        setTimeout(() => resolve({
          loadedPosts: [
            { id: '1', title: 'First Post', previewText: 'So it has come to my attention recen...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
            { id: '2', title: 'Second Post', previewText: 'Until recently I has assumed that it w...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
          ]
        }), 2000);
      }).catch(e => {
        context.error(new Error());
      })
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