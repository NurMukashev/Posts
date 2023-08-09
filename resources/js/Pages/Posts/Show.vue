<template>
    <h1 class="text-lg mb-2">Post</h1>
    <div class="mb-2">
        <Link :href="route('posts.index')" class="text-sm text-green-700">Back</Link>
    </div>
    <div v-if="post">
        <div class="mt-4 pt-4 border-t border-gray-500">
            <div>id: {{ post.id }}</div>
            <div>name: {{ post.name }}</div>
            <div>text: {{ post.text }}</div>
            <div class="text-sm text-right">{{ post.date }}</div>
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
        'post'
    ],
}
</script>

<style scoped>

</style>
