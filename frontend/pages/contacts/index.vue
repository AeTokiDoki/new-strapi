<template>
  <div class="app">
    <nuxt-link class="link" to="/">Назад</nuxt-link>

    <h1>Контакты</h1>
    <div>
      <p><b>Почта:</b> example@mail.ru</p>
      <p><b>Телефон:</b> +993555666</p>
      <p>
        <nuxt-link class="link links" to="#">WK</nuxt-link>
      </p>
      <p>
        <nuxt-link class="link links" to="#">Instagram</nuxt-link>
      </p>
      <p>
        <nuxt-link class="link links" to="#">Telegram</nuxt-link>
      </p>
    </div>
  </div>
</template>

<style scoped>
.link {
  text-decoration: none;
  margin-bottom: 30px;
}
.links {
  color: coral;
}
.app {
  width: 80vh;
  margin: 0 auto;
}
</style>
