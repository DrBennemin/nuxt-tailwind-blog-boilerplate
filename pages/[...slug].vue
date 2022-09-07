<script setup>
const { path } = useRoute();
const { data: blogPost } = await useAsyncData(`content-${path}`, () => {
    return queryContent().where({ _path: path }).findOne();
});
</script>
<template>
    <main>
        <div class="container prose prose-red">
            <ContentDoc />
        </div>
    </main>
</template>
