<template>
  <v-row>
    <v-col class="text-center">
      <img src="/v.png" alt="Vuetify.js" class="mb-5" />
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
        </footer>
      </blockquote>
    </v-col>
    <v-col class="text-center">{{ user }} </v-col>
  </v-row>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const data = await $axios.$get('/api/users')
    return {
      user: data,
    }
  },
  head() {
    return {
      title: 'Users',
    }
  },
}
</script>
