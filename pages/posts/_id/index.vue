<template>
    <div class="single-post-page">
        <section class="post">
            <h1 class="post-title">{{loadedPost.title}}</h1>
            <div class="post-details">
                <div class="post-detail">
                    Last updated on {{loadedPost.updatedDate}}
                    <br>
                    <br>
                    - {{loadedPost.author}}
                </div>
                
            </div>
            <p class="content">{{post.previewText}}</p>
        </section>
        <section class="post-feedback">
            <p>Let me know what you think about the post. Send some mail to <a href="mailto:feedback@website.com">feedback@website.com</a></p>
        </section>
    </div>
</template>

<script>
export default {
    data() {
      return {
        id: this.$route.params.id
      }
    },
    computed: {
      post () {
        return this.$store.state.posts.allPosts.find(post => post.id === this.id)
      }
    },
    asyncData(context, callback) {
      setTimeout(() => {
        callback(null, {
          loadedPost: { 
            id: '1',
            title: 'First TIL (ID: ' + context.params.id +')',
            author: 'Brandon',
            updatedDate: new Date(),
            content: 'Text content should go here.',
            previewText: 'So it has come to my attention recen...', 
            thumbnail: 'https://source.unsplash.com/featured/?tech' 
          }
        });
        // this.$route.params
      }, 1000);
    }
}
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>