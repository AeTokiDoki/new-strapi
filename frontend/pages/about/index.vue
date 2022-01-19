<template>
  <div class="app">
    <nuxt-link class="link" to="/">Назад</nuxt-link>
    <h1>{{ fio }}</h1>
    <div>{{ inform }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fio: null,
      inform: null,
      error: null,
    };
  },
  async mounted() {
    try {
      this.abouts = await this.$strapi.$abouts.find();
      this.fio = this.abouts[0].FIO;
      this.inform = this.abouts[0].inform;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  },
};
</script>

<style scoped>
.link {
  text-decoration: none;
}
.app {
  width: 80vh;
  margin: 0 auto;
}
</style>
