<template>
    <div>
        <h2>Articles</h2>
        <div class='grid grid-cols-4 gap-5'>
             <div v-for='a in articles'>
                <ArticleCard :article='a'/>
             </div>
        </div>
        <Pagination :nextPage="nextPage" :pageNo="1" urlPrefix="/articles" />
    </div>
</template>

<script setup lang='ts'>

import Pagination from '~/components/Pagination.vue';

    const page = ref(1);
    const { data: articles } = await useFetch('https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/');



</script>

<style scoped>
    h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
</style>