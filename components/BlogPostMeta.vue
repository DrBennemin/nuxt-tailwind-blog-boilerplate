<script setup>
const props = defineProps({
    author: {
        type: String,
        required: true,
    },
    date: {
        type: String,
        required: true,
    },
});
const formattedDate = computed(() => {
    return new Date(props.date).toDateString();
});
</script>

<template>
    <div class="">
        <span class="">{{ author }}</span>
        <span class="">{{ formattedDate }}</span>
    </div>
</template>
