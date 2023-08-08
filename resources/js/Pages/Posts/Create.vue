<template>
    <div class="w-3/4 mx-auto pt-6">
        <h1 class="text-lg mb-5">Create</h1>
        <form @submit.prevent="store">
            <div class="mb-4">
                <input v-model="name" type="text" placeholder="title" class="w-full border-green-700">
            </div>
            <div class="mb-4">
                <textarea v-model="text" placeholder="content" cols="30" rows="10" class="w-full border-green-700"></textarea>
            </div>
            <div>
                <button type="submit" class="ml-auto hover:bg-white hover:text-green-700 block p-2 w-48 border border-green-700 bg-green-700 rounded text-center text-white">Store</button>
            </div>
        </form>
    </div>
</template>

<script>
import {Link} from "@inertiajs/vue3";
export default {
    name: "index",
    components: {
        Link
    },

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
