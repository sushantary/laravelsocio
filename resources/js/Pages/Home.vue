<script setup>
import { Head } from '@inertiajs/vue3';
import GroupList from "@/Components/app/GroupList.vue";
import PostItems from "@/Components/app/PostItems.vue";
import FollowerItems from "@/Components/app/FollowerItems.vue";


defineProps({

})
</script>

<template>

    <Head title="Home" />
    <div class="grid grid-cols-12 gap-3">
        <div class="col-span-3 border-inherit rounded bg-gray-50 py-6 px-3">
            <group-list />
        </div>
        <post-items />
        <follower-items />


    </div>
</template>

<style></style>
