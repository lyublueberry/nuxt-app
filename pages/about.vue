<template>
  <div>
    <h1>Здесь можно увидеть информацию обо мне</h1>
    <p>Я frontend-разработчик с профильным образованием и коммерческим опытом работы</p>
    <p></p>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.message }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  middleware:['auth'],
  data() {
    return {
      items: [
      {id: 1, message: 'Писала код c 0 на стеке Vue.js 2 (Option API) & JS, создавая новый сервис, исправляла баги и делала доработки в уже существующем коде, работала с Vuex, vue-router, Vuelidate, Vuetify, BootstrapVue;' },
      {id:2, message: 'Кроссбраузерно адаптивно верстала с использованием SASS/SCSS, JS, jQuery и различных плагинов, в том числе работала с библиотекой графиков amcharts5.js' },
      {id:3, message: 'Умею работать с Git, Jira, Confluence, Docker, npm, yarn, Pug, Vue CLI, PostgreSQL и MySQL, писать SQL запросы, составлять UML диаграммы проектов'},
      {id:4, message: 'Изучила Nuxt.js, React, Vue3 (Composition API), Vue-CLI, TypeScript;'}
    ]
    }
  },
}
</script>

