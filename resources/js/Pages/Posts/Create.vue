<template>
    <h1 class="text-lg mb-2">Create</h1>
    <div class="mb-2">
        <Link :href="route('posts.index')" class="text-sm text-green-700">Back</Link>
    </div>
    <form @submit.prevent="store">
        <div class="mb-4">
            <input v-model="name" type="text" placeholder="title" class="w-full border-green-700">
            <div v-if="errors.name" class="text-red-500 text-sm">{{ errors.name }}</div>
        </div>
        <div class="mb-4">
            <textarea v-model="text" placeholder="content" cols="30" rows="10" class="w-full border-green-700"></textarea>
            <div v-if="errors.text" class="text-red-500 text-sm">{{ errors.text }}</div>
        </div>
        <div>
            <button type="submit" class="ml-auto hover:bg-white hover:text-green-700 block p-2 w-48 border border-green-700 bg-green-700 rounded text-center text-white">Store</button>
        </div>
    </form>
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

    props: [
        'errors'
    ],

    data () {
        return {
            name: '',
            text: '',
        }
    },

    methods: {
        store() {
            this.$inertia.post('/posts', {name: this.name, text: this.text})
        }
    }
}
</script>

<style scoped>

</style>
