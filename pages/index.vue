<template>
  <div class="home-page">
    <section class="intro">
      <h1>Today I learned...</h1>
    </section>
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
          { id: '1', title: 'First TIL', previewText: 'So it has come to my attention recen...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
          { id: '2', title: 'Second TIL', previewText: 'Until recently I has assumed that it w...', thumbnail: 'https://source.unsplash.com/featured/?tech' },
        ]
      }), 1500)
    })
  },
  // data() {
  //   return {
  //     loadedPosts: []
  //   }
  // },
  created() {
    
  }
}
</script>

<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-image: url('~assets/images/coding.jpg');
  background-position: center;
  background-size: cover;
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}


</style>