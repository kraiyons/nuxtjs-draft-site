<template>
  <div>
    <h1>Blog posts</h1>
    <p v-if="$fetchState.pending">Fetching posts...</p>
    <p v-else-if="$fetchState.error">
      Error while fetching posts: {{ $fetchState.error.message }}
    </p>
    <ul v-else>
      <li v-for="post of posts" :key="post.id">
        <n-link :to="`/posts/${post.id}`">{{ post.title }}</n-link>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from axios;
  export default {
    data() {
      return {
        posts: []
      }
    },
    async fetch() {
      this.posts = await fetch(
        'https://jsonplaceholder.typicode.com/posts', {
          'method': 'GET'
        }
      )
    }
  }
</script>