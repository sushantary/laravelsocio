<script setup>
import {Disclosure, DisclosureButton, DisclosurePanel} from "@headlessui/vue";

defineProps({
    post: Object,
})
</script>

<template>
    <div class="bg-white border rounded px-4 py-4 mb-2 shadow-md hover:bg-indigo-50">
        <div class="flex mb-3 items-center">
            <a href="javascript:void(0)">
                <img :src="post.user.avatar" alt="users avatar" class="rounded-full w-[48px] mb-2"/>
            </a>
            <div>
                <h4 class="font-bold">
                    <a href="javascript:void(0)">{{ post.user.name }}</a>
                </h4>
                <small class="text-gray-400 ml-2">{{ post.created_at }}</small>
            </div>
        </div>
        <div>
            <Disclosure v-slot="{ open }">
                <div v-if="!open" class="mt-2 mb-4" v-html="post.body.substring(0,250)"/>
                <DisclosurePanel>
                    <div class="mt-2 mb-2" v-html="post.body"/>
                </DisclosurePanel>
                <div class="flex justify-end">
                    <DisclosureButton class="text-blue-500 border-black rounded-md hover:text-blue-600 ">
                        {{ open ? 'Read Less' : 'Read More' }}
                    </DisclosureButton>
                </div>
            </Disclosure>

        </div>
    </div>
</template>

<style>

</style>
