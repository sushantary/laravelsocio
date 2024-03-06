<script setup>
import { Head } from '@inertiajs/vue3';
import GroupList from "@/Components/app/GroupList.vue";
import PostList from "@/Components/app/postList.vue";
import FollowingList from "@/Components/app/FollowingList.vue";
import CreatePost from "@/Components/app/CreatePost.vue";


defineProps({

})
</script>

<template>

    <Head title="Home" />
    <div class="grid grid-cols-12 gap-3">
        <div class="col-span-3 bg-gray-50">
            <group-list />
        </div>
        <div class="col-span-6 bg-gray-50">
            <div>
                <create-post />
            </div>
            <post-list />
        </div>
        <div class="col-span-3 bg-red-50 ">
            <following-list />
        </div>


    </div>
</template>

<style></style>
