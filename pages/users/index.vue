<template>
  <div>
    <h1>Список пользователей</h1>
    <span>Нажав на пользователя, сможете увидеть подробную информацию о нём</span>

    <ul>
      <li v-for="user of users" :key="user.id">
        <a href="#" @click.prevent="openUser(user)"> {{ user.name }}</a>
      </li>

    </ul>
  </div>
</template>
<script>
export default {
  async fetch({ store }) {
    if (store.getters['users/users'].length === 0) {
      await store.dispatch('users/fetch')
    }
  },
  data: () => {
    return {}
  },
  computed:{
    users(){
      return this.$store.getters['users/users'];
    }
  },
  methods: {
    openUser(user) {
      this.$router.push('/users/' + user.id)
    }
  }
}
</script>
