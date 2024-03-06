<script setup>
defineProps({
    image: String,
    title: String,
})
</script>

<template>
    <div class="px-3">
        <div class=" mb-3 hover:bg-indigo-100 rounded-xl cursor-pointer">
            <div class="flex items-start gap-2  px-2 py-2">
                <img :src="image" alt="random img" class="w-[48px] rounded-full"/>
                <div>
                    <h3 class="font-black text-lg">{{ title }}</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
