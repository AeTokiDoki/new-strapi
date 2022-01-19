<template>
  <div class="app">
    <nuxt-link class="link" to="/">Назад</nuxt-link>

    <h1>Контакты</h1>
    <div>
      <p><b>Почта:</b> {{ email }}</p>
      <p><b>Телефон:</b> {{ tel }}</p>
      <p>
        <a class="link links" :href="insta">Instagram</a>
      </p>
      <p>
        <a class="link links" :href="wk">wk</a>
      </p>
      <p>
        <a class="link links" :href="telegram">telegram</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: null,
      tel: null,
      insta: null,
      wk: null,
      telegram: null,
      error: null,
    };
  },
  async mounted() {
    try {
      this.contacts = await this.$strapi.$contacts.find();
      this.email = this.contacts[0].email;
      this.tel = this.contacts[0].tel;
      this.insta = this.contacts[0].insta;
      this.wk = this.contacts[0].wk;
      this.telegram = this.contacts[0].telegram;
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
