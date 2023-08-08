<template>
    <div class="w-3/4 mx-auto pt-6">
        <h1 class="text-lg mb-5">Posts</h1>
        <div>
            <Link :href="route('posts.create')" class="hover:bg-white hover:text-green-700 block p-2 w-48 border border-green-700 bg-green-700 rounded text-center text-white" >Add Post</Link>
        </div>
    </div>
</template>

<script>
import {Link} from "@inertiajs/vue3";
export default {
    name: "index",
    components: {
        Link
    }
}
</script>

<style scoped>

</style>
