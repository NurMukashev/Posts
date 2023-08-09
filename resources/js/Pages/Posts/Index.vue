<template>
    <h1 class="text-lg mb-5">Posts</h1>
    <div class="mb-6">
        <Link :href="route('posts.create')" class="hover:bg-white hover:text-green-700 block p-2 w-48 border border-green-700 bg-green-700 rounded text-center text-white" >Add Post</Link>
    </div>
    <div v-if="posts">
        <div class="mt-4 pt-4 border-t border-gray-500" v-for="post in posts">
            <div>id: {{ post.id }}</div>
            <div>name: {{ post.name }}</div>
            <div>text: {{ post.text }}</div>
            <div class="text-sm text-right">{{ post.date }}</div>
            <div class="text-sm text-right">
                <Link class="text-green-700" :href="route('posts.show', post.id)">Show</Link>
            </div>
            <div class="text-sm text-right">
                <Link class="text-green-700" :href="route('posts.edit', post.id)">Edit</Link>
            </div>
        </div>
    </div>
</template>

<script>
import {Link} from "@inertiajs/vue3";
import MainLayout from "@/Layouts/MainLayout.vue";
export default {
    name: "index",
    layout: MainLayout,
    components: {
        Link
    },
    props:[
        'posts'
    ],
}
</script>

<style scoped>

</style>
