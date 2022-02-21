<template>
  <v-footer
    color="primary lighten-1"
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
        to="\www.linkedin.com/in/ronaldo-martins-da-silva-a07131122/"
        target="_blank"
      >
        {{ link }}
      </v-btn>
      <v-col
        class="primary lighten-2 py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Ronaldo Martins</strong>
      </v-col>
    </v-row>
  </v-footer>
</template>
<script>
  export default {
    data: () => ({
      links: [
        'GitHub',
        'Sobre',
        'Linkdin',
        'Services',
        'Blog',
        'Fone',
      ],
    }),
  }
</script>