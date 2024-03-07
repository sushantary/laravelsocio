<script setup>
import {Disclosure, DisclosureButton, DisclosurePanel} from "@headlessui/vue";
import {ref} from "vue";

defineProps({
    posts: Object,
})

function isImage(attachment) {
    const mine = attachment.mime.split('/')
    return mine[0].toLowerCase() === 'image'
}

const isClicked = ref(false)

function toggleSizeAndColor() {
    isClicked.value = !isClicked.value;
}
</script>

<template>
    <div class="bg-white border rounded px-4 py-4 mb-2 shadow-sm">
        <div class="flex mb-3 items-center">
            <a href="javascript:void(0)">
                <img :src="posts.user.avatar" alt="users avatar"
                     class="rounded-full w-[44px] mb-2 border-2 transition-all hover:border-blue-400"/>
            </a>
            <div>
                <h4 class="font-bold ml-2">
                    <a class="hover:underline" href="javascript:void(0)">{{ posts.user.name }} </a>
                    <template v-if="posts.group">
                        <a class="hover:underline" href="javascript:void(0)"> -> {{ posts.group.name }}</a>
                    </template>
                </h4>
                <small class="text-gray-400 ml-2">{{ posts.created_at }}</small>
            </div>
        </div>
        <div>
            <Disclosure v-slot="{ open }">
                <div v-if="!open" class="mt-2 mb-4" v-html="posts.body.substring(0,250)"/>
                <DisclosurePanel>
                    <div class="mt-2 mb-2" v-html="posts.body"/>
                </DisclosurePanel>
                <div class="flex justify-end">
                    <DisclosureButton class="text-blue-500 border-black rounded-md hover:text-blue-600 hover:underline">
                        {{ open ? 'Read Less' : 'Read More' }}
                    </DisclosureButton>
                </div>
            </Disclosure>
        </div>
        <div class="grid grid-cols-2 gap-3">
            <div v-for="attachment of posts.attachments">
                <img
                    v-if="isImage(attachment)"
                    :src="attachment.url"
                    alt="attachment"
                    class="mt-2 object-cover aspect-square">
                <div v-else
                     class="object-cover aspect-square bg-blue-100 flex flex-col items-center justify-center text-gray-400">
                    <svg class="w-16 h-16 " fill="currentColor" viewBox="0 0 24 24"
                         xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M5.625 1.5c-1.036 0-1.875.84-1.875 1.875v17.25c0 1.035.84 1.875 1.875 1.875h12.75c1.035 0 1.875-.84 1.875-1.875V12.75A3.75 3.75 0 0 0 16.5 9h-1.875a1.875 1.875 0 0 1-1.875-1.875V5.25A3.75 3.75 0 0 0 9 1.5H5.625Z"/>
                        <path
                            d="M12.971 1.816A5.23 5.23 0 0 1 14.25 5.25v1.875c0 .207.168.375.375.375H16.5a5.23 5.23 0 0 1 3.434 1.279 9.768 9.768 0 0 0-6.963-6.963Z"/>
                    </svg>

                    {{ attachment.name }}
                </div>
            </div>
        </div>
        <div class="mt-4">
            <div
                class="flex justify-between items-center border-solid border-2 border-gray-100 bg-gray-50 rounded-full m-2 p-2">
                <button :class="{'transform scale-110 text-red-500': isClicked}" class="transition-transform"
                        @click="toggleSizeAndColor">
                    <svg class="w-7 h-7" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path
                            :class="{'scale-130': isClicked}"
                            d="m11.645 20.91-.007-.003-.022-.012a15.247 15.247 0 0 1-.383-.218 25.18 25.18 0 0 1-4.244-3.17C4.688 15.36 2.25 12.174 2.25 8.25 2.25 5.322 4.714 3 7.688 3A5.5 5.5 0 0 1 12 5.052 5.5 5.5 0 0 1 16.313 3c2.973 0 5.437 2.322 5.437 5.25 0 3.925-2.438 7.111-4.739 9.256a25.175 25.175 0 0 1-4.244 3.17 15.247 15.247 0 0 1-.383.219l-.022.012-.007.004-.003.001a.752.752 0 0 1-.704 0l-.003-.001Z"/>
                    </svg>
                </button>
                <button>
                    <svg class="w-7 h-7 bg-red-50"
                         fill="currentColor"
                         viewBox="0 0 24 24"
                         xmlns="http://www.w3.org/2000/svg"
                    >
                        <path clip-rule="evenodd"
                              d="M4.804 21.644A6.707 6.707 0 0 0 6 21.75a6.721 6.721 0 0 0 3.583-1.029c.774.182 1.584.279 2.417.279 5.322 0 9.75-3.97 9.75-9 0-5.03-4.428-9-9.75-9s-9.75 3.97-9.75 9c0 2.409 1.025 4.587 2.674 6.192.232.226.277.428.254.543a3.73 3.73 0 0 1-.814 1.686.75.75 0 0 0 .44 1.223ZM8.25 10.875a1.125 1.125 0 1 0 0 2.25 1.125 1.125 0 0 0 0-2.25ZM10.875 12a1.125 1.125 0 1 1 2.25 0 1.125 1.125 0 0 1-2.25 0Zm4.875-1.125a1.125 1.125 0 1 0 0 2.25 1.125 1.125 0 0 0 0-2.25Z"
                              fill-rule="evenodd"/>
                    </svg>
                </button>
                <button>
                    <svg class="w-7 h-7" viewBox="0 0 24 24"
                         xmlns="http://www.w3.org/2000/svg">
                        <path clip-rule="evenodd"
                              d="M15.75 4.5a3 3 0 1 1 .825 2.066l-8.421 4.679a3.002 3.002 0 0 1 0 1.51l8.421 4.679a3 3 0 1 1-.729 1.31l-8.421-4.678a3 3 0 1 1 0-4.132l8.421-4.679a3 3 0 0 1-.096-.755Z"
                              fill-rule="evenodd"/>
                    </svg>
                </button>
            </div>
        </div>
    </div>
</template>

<style>
.transition-transform {
    transition-property: transform;
}

@keyframes bounce {
    0%, 20%, 50%, 80%, 100% {
        transform: scale(1);
    }
    40% {
        transform: scale(1.1);
    }
    60% {
        transform: scale(0.9);
    }
}

.scale-130 {
    animation: bounce 1s ease-in-out;
}
</style>
