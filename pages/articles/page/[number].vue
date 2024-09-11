<template>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Pagination :prevPage="pageNo > 1" :nextPage="nextPage" :pageNo="pageNo" urlPrefix="/articles" />
    </div>
  </template>
  
  <script>
  export default {
    async asyncData({ $content, params, error }) {
      const pageNo = parseInt(params.number)
      const tenArticles = await $content('articles')
        .only(['title', 'description', 'img', 'slug', 'tags'])
        .sortBy('createdAt', 'desc')
        .limit(10)
        .skip(9 * (pageNo - 1))
        .fetch()
  
      if (!tenArticles.length) {
        return error({ statusCode: 404, message: 'No articles found!' })
      }
  
      const nextPage = tenArticles.length === 10
      const articles = nextPage ? tenArticles.slice(0, -1) : tenArticles
  
      return {
        nextPage,
        articles,
        pageNo
      }
    },
  }
  </script>