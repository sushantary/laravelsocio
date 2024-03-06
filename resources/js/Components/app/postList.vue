<script setup>

import PostItems from "@/Components/app/PostItems.vue";

const post1 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/11.jpg',
        name: "John Smith"
    },
    group: null,
    body: `<p>lorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
 sit amet loremlorem ipsum dolor sit amet lorem</p>

<p>lorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
 sit amet loremlorem ipsum dolor sit amet lorem</p>`,
    created_at: "2022-01-01 00:00:00",
}
const post2 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/21.jpg',
        name: "John Doe"
    },
    group: null,
    body: `<p>lorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
 sit amet loremlorem ipsum dolor sit amet lorem</p>

<p>lorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor sit amet loremlorem ipsum dolor
 sit amet loremlorem ipsum dolor sit amet lorem</p>`,
    created_at: "2022-01-01 00:00:00",
}


</script>
<template>
    <div class="px-3">
        <div>
            <post-items :post='post1'/>
            <post-items :post='post2'/>

        </div>
    </div>
</template>
<style scoped>
</style>
