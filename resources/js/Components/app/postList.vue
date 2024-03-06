<script setup>

import PostItems from "@/Components/app/PostItems.vue";

const getRandomParagraph = () => {
    const numSentences = Math.floor(Math.random() * 5) + 1; // Generate a random number of sentences between 1 and 5
    const sentenceTypes = [
        "He watched as the young man tried to impress everyone in the room with his intelligence. There was no doubt that he was smart.  only cared about his intelligence.",
        "Cake or pie? I can tell a lot about you by which one you pick. It may seem silly, but cake people and pie people are really different. I know which one I hope you are, but that's not for me to decide. So, what is it? Cake or pie?",
        "She considered the birds to be her friends. She'd put out food for them each morning and then she'd watch as they came to the feeders to gorge themselves for the day. She wondered what they would do if something ever happened to her. Would they miss the meals she provided if she failed to put out the food one morning?",
        "Her eyebrows were a shade darker than her hair. They were thick and almost horizontal, emphasizing the depth of her eyes. She was rather handsome than beautiful. Her face was captivating by reason of a certain frankness of expression and a contradictory subtle play of features. Her manner was engaging.",
        "It's always good to bring a slower friend with you on a hike. If you happen to come across bears, the whole group doesn't have to worry. Only the slowest in the group do. That was the lesson they were about to learn that day.",
        "Humility is the practice of recognizing our limitations and imperfections, and it is essential to personal growth and development. Whether it's acknowledging our mistakes and shortcomings, seeking feedback from others, or approaching new situations with a sense of openness and curiosity, humility can help us learn and grow in meaningful ways.",
        "The use of biotechnology in agriculture is another exciting development. Biotechnology can be used to create more resilient crops, reduce pesticide use, and increase food production."
    ];
    const sentences = [];
    for (let i = 0; i < numSentences; i++) {
        const randomIndex = Math.floor(Math.random() * sentenceTypes.length);
        sentences.push(sentenceTypes[randomIndex]);
    }
    return sentences.join(" ");
};
const post1 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/11.jpg',
        name: "John Smith"
    },
    group: {
        id: 1,
        name: "Group 1"
    },
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post2 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/21.jpg',
        name: "John Doe"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post3 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/3.jpg',
        name: "yubraj"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post4 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/2.jpg',
        name: "Salam"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post5 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/16.jpg',
        name: "Shah rukh"
    },
    group: {
        id: 1,
        name: "Laravel Developer"
    },
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post6 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/15.jpg',
        name: "Ms Dhoni"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post7 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/22.jpg',
        name: "Virat"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post8 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/1.jpg',
        name: "Sheldon"
    },
    group: null,
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
const post9 = {
    user: {
        id: 1,
        avatar: 'https://randomuser.me/api/portraits/men/31.jpg',
        name: "JDoe"
    },
    group: {
        id: 2,
        name: "Laravel Developer",
    },
    body: getRandomParagraph(),
    created_at: "2022-01-01 00:00:00",
}
</script>
<template>
    <div class="px-3">
        <div>
            <post-items :post='post1'/>
            <post-items :post='post2'/>
            <post-items :post='post3'/>
            <post-items :post='post4'/>
            <post-items :post='post5'/>
            <post-items :post='post6'/>
            <post-items :post='post7'/>
            <post-items :post='post8'/>
            <post-items :post='post9'/>


        </div>
    </div>
</template>
<style scoped>
</style>
