<template>
    <div class="container">
        <div class="row d-flex justify-content-center">
            <div class="col-sm-8">
                <h1 class="text-primary text-center mt-3 mb-3">
                    {{ post.titulo }}
                </h1>
                <p class="text-default">
                    {{ post.texto }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>

import { useRoute } from 'vue-router'
import posts from '@/assets/posts.json'

export default {
    name:'PostView',
    data() {
        return {
            post_id: 0
        }
    },
    created() {
        const route = useRoute()
        this.post_id = route.params.id
        console.log(this.post_id)
    },
    computed: {
        posts() {
            return posts
        },
        post() {
            return this.posts.find((element) => element.id == this.post_id)
        }
    }
}

</script>