<script setup>
defineProps({
    post: Object,
})
</script>

<template>
    <div>
        <div class="flex mb-2 items-center">
            <a href="javascript:void(0)">
                <img :src="post.user.avatar" alt="users avatar" class="rounded-full w-[48px] mb-2"/>

            </a>
            <div>
                <a href="javascript:void(0)">
                    <h4 class="ml-2">{{ post.user.name }}</h4>
                </a>
                <small class="text-gray-400 ml-2">{{ post.created_at }}</small>
            </div>
        </div>
        <div class="mt-2 mb-4" v-html="post.body">
        </div>

    </div>
</template>

<style scoped>

</style>
