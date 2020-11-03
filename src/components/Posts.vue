<template>
  <div class="hello">
    <div class="posts" v-for="post in posts" :key="post">
      {{post.title}}
    </div>
  </div>
</template>

<script>

import axios from 'axios';

const baseUrl = 'https://jsonplaceholder.typicode.com';

export default {
  data() {
    return {
      posts: [],
    }
  },
  computed: {

  },
  methods: {
    GetPosts() {
      axios
      .get(`${baseUrl}/posts`)
      .then(response => (this.posts = response.data));
    },
  },
  mounted(){
    this.GetPosts();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
