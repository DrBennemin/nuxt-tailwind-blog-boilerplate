<script setup>
const { data: blogPostList } = useAsyncData("blogPostList", () => {
    return queryContent("/blog").find();
});
</script>
<template>
    <div class="container mx-auto">
        <div v-for="blogPost in blogPostList" :key="blogPost._path">
            <NuxtLink :to="blogPost._path">
                <section class="shadow-xl rounded-md mb-12 p-8">
                    <div class="">
                        <h3 class="pb-4">
                            {{ blogPost.title }}
                        </h3>
                        <BlogPostMeta :author="blogPost.author" :date="blogPost.dates.published" />
                    </div>
                    <div class="pt-4">
                        {{ blogPost.description }}
                    </div>
                </section>
            </NuxtLink>
        </div>
    </div>
</template>
