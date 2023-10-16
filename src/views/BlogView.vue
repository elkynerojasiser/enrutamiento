<template>
    <div class="container">
        <div class="row d-flex justify-content-center m-3 p-3">
            <div class="col-sm-8">
                <h1 class="text-center text-primary">
                    Blog
                </h1>
            </div>
        </div>
        <div class="row d-flex justify-content-center m-3 p-3">
            <div v-for="post in posts" :key="post.id" class="col-sm-8">
                <div class="card mt-3 mb-3 p-3">
                    <div class="title">
                        <router-link :to="{name:'post',params:{id:post.id}}">{{ post.titulo }}</router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
</template>

<script>
import posts from '@/assets/posts.json'

export default {
    name: 'BlogView',
    
    computed: {
        posts() {
            return posts
        }
    }
}
</script>


<style>
</style>