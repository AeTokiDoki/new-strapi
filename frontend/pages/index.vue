<template>
  <div class="app">
    <main class="main">
      <h1>Главная страница</h1>
      <h2>{{ name }}</h2>
      <div>
        <img :src="img" alt="avatar" />
      </div>

      <nuxt-link class="link" to="/about">Обо мне</nuxt-link>
      <nuxt-link class="link" to="/contacts">Контакты</nuxt-link>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      img: null,
      name: null,
      error: null,
    };
  },
  async mounted() {
    try {
      this.mains = await this.$strapi.$mains.find();
      this.name = this.mains[0].name;
      this.img = this.mains[0].photo;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  },
};
</script>


<style scoped>
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, sans-serif;
  text-align: center;
  background: #ddd;
}
.app {
  width: 80vh;
  margin: 0 auto;
}
h1,
h2 {
  margin-bottom: 30px;
}
.main {
  display: flex;
  flex-direction: column;
}
.link {
  text-decoration: none;
  color: tomato;
}
img {
  height: 20vh;
  width: 20vh;
}
</style>
