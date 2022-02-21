<template>
  <v-app>
    <v-main>
      <v-container>
        <v-card elevation="19" loading>
          <v-card-actions>IMC</v-card-actions>
           <v-card-actions>Índice de Massa Corporal</v-card-actions>
          <v-card-actions v-if="total != 0">Resultado: {{ total }}</v-card-actions>
          <v-card-actions v-if="total != 0">Classificação: {{ status }}</v-card-actions>
          <v-text-field
            v-model="altura"
            label="Altura"
            filled
            placeholder="1.75"
          ></v-text-field>
          <v-text-field
            v-model="peso"
            label="Peso"
            filled
            placeholder="85.0"
          ></v-text-field>
          <v-btn
            color="success"
            class="ma-2 white--text"
            @click="Calcular"
            >Calcular</v-btn
          >
        </v-card>
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>
<script>
import Footer from './components/Footer.vue';
export default {
  components: { Footer },
  data() {
    return {
      altura: 0,
      peso: 0,
      total: 0,
      status: "",
    };
  },
  methods: {
    Calcular() {
      if (this.altura && this.peso > 0) {
        this.total = this.peso / this.altura ** 2;
        if (this.total < 18.05) this.status = "Abaixo do Peso";
        else if (this.total < 24.09) this.status = "Saudável";
        else if (this.total < 25.09) this.status = "Excesso de peso";
        else if (this.total < 30.0) this.status = "Obesidade Grau I";
        else if (this.total < 35.0) this.status = "Obesidade Grau II";
        else if (this.total >= 40.0) this.status = "Obesidade Grau III";
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: aliceblue;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
