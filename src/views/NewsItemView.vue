<template>
  <div class="current-news-item">
    <h2 v-if="loading">Loading...</h2>
    <div v-if="!loading">
      <news-item :item="currentNewsItem" />
      <comment v-for="comment in currentNewsItem.comments" :key="comment.id" :data="comment" />
    </div>
  </div>
</template>

<script>
import { onCreated } from 'vue-function-api';
import { useState, useActions, useRouter } from '@u3u/vue-hooks';

import types from '../types';
import NewsItem from '../components/NewsItem.vue';

export default {
  components: {
    NewsItem,
  },
  setup() {
    const { route } = useRouter();
    const { loading, currentNewsItem } = useState(['loading', 'currentNewsItem']);

    const { GET_NEWS_ITEM } = useActions([types.GET_NEWS_ITEM]);

    onCreated(() => {
      GET_NEWS_ITEM(route.value.params.id);
    });

    return {
      loading,
      currentNewsItem,
    };
  },
};
</script>

<style>
.current-news-item {
  counter-reset: news;
  background-color: #f6f6ef;
  padding: 1em;
}

.current-news-item .news-item-title::before {
  content: none;
}
</style>
