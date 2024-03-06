<script setup>

import {ref} from "vue";

const postCreating = ref(false);
</script>

<template>
    <div class="py-6">
        <div class="py-3 px-2 text-gray-800" @click="postCreating = true">
            <h3>Post</h3>
            <textarea id="about"
                      class="relative block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      name="about"
                      placeholder="share your post"></textarea>
        </div>
        <div v-if="postCreating" class="mt-6 flex items-center justify-end gap-x-2">
            <button
                class="rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 relative">
                Attach File
                <input class="absolute left-0 right-0 top-0 bottom-0 opacity-0" type="file">
            </button>
            <button
                class="rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 mr-2"
                type="submit">
                Post
            </button>
        </div>
    </div>
</template>
