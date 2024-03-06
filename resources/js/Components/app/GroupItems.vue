<script setup>
defineProps({
    image: String,
    title: String,
    description: String,
})
</script>
<template>
    <div class=" mb-3 hover:bg-gray-200  cursor-pointer">
       <div class="flex items-start gap-1  px-2 py-2">
           <img :src="image" class="w-[48px] rounded-full" alt="random img"/>
        <div>
           <h3 class="font-black text-lg">{{ title }}</h3>
           <p class="text-gray-600 font-semi-bold">{{ description }}</p>
        </div>
       </div>
    </div>
</template>

<style scoped>

</style>

