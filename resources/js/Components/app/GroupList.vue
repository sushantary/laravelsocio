<script setup>

import TextInput from "@/Components/TextInput.vue";
import GroupItems from "@/Components/app/GroupItems.vue";
import {ref} from "vue";

const searchKeyword = ref('')

</script>

<template>

    <div class="px-3">
        <h1 class="text-2xl font-bold py-6 px-3">My Groups</h1>
        <TextInput :model-value="searchKeyword" placeholder='Type to search'/>
        <div class="py-8 px-3">
            <div v-if="false" class="text-gray-600 flex text-center">
                you are not joined to any of your groups
            </div>
            <div v-else>
                <GroupItems description="laravel framework is based on the following image"
                            image="https://picsum.photos/220"
                            title="Laravel Developers"
                />

                <GroupItems description="Vue  is based on the following image"
                            image="https://picsum.photos/220"
                            title="Vue js Developers"
                />
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
