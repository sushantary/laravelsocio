<script setup>

import TextInput from "@/Components/TextInput.vue";
import {ref} from "vue";
import FollowingItem from "@/Components/app/FollowingItem.vue";
const searchKeyword = ref('')
</script>

<template>
    <div class="px-3">
        <h1 class="text-2xl font-bold py-6 px-3">My Friends</h1>
        <TextInput :model-value="searchKeyword" placeholder = 'Type to search' class="w-max" />
        <div class="py-8 px-3">
            <div v-if="false" class="text-gray-600 flex text-center">
                you don't have friends yet.
            </div>
            <div v-else>
                <following-item image="https://picsum.photos/120"
                            title="John Smith"
                />
                <following-item image="https://picsum.photos/320"
                            title="John Doe"
                />
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
