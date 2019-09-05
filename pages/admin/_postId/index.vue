<template>
    <div class="admin-post-page">
        <section class="update-form">
            <AdminPostForm 
            :post="loadedPost"
            />
        </section>
    </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'
    export default {
        components: {
            AdminPostForm
        },
        data() {
            return {
                loadedPost: {
                    author: 'Brandon',
                    title: 'My Post',
                    content: 'Some stuff should go here.',
                    thumbnailLink: 'https://miro.medium.com/max/798/1*EWDEUt0fqsmRgpYGFOOMew.png'
                }
            }
        }
    }
</script>

<style scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}
@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>