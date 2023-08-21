<template>
  <div>
    <h1>{{ user.name }}</h1>
    <h2>{{ user.username }}</h2>
    <h3>{{ user.email }}</h3>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    return true;
  },
  async asyncData({ $axios, params }) {
    const user = await $axios.$get('https://jsonplaceholder.typicode.com/users/' + params.id);
    return { user };
  },
}


</script>
