<template>
  <section class="home">
    <div class="header"></div>
    <p class="rocket">🚀</p>
    <h1>Test Front-End Databot</h1>
    <h3 class="text-center">Víncula la API de la NASA 👇</h3>
    <div class="container">
      <div class="info_box">
        <Cards :dataNasaProps="dataNasa" />
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import Cards from "../components/Cards.vue";

export default {
  name: "Home",
  components: {
    Cards,
  },
  data() {
    return {
      dataNasa: [],
    };
  },
  async mounted() {
    await this.getNasaInfo();
  },
  methods: {
    async getNasaInfo() {
      const response = await axios.get("https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&api_key=00MpcQQ8jsIc7pY6ORQd2WJFII9Sn7XczchfzREm");
      this.dataNasa = response.data.photos;
    },
  },
};
</script>

<style scoped>
.header {
  background-color: #2981ef;
  height: 75px;
}
.rocket {
  font-size: 55px;
  margin: 5rem auto 0.5rem;
}
h1 {
  font-size: 55px;
  margin: 1rem auto 0.5rem;
}
.info_box {
  border: 1px dashed #cdcdcd;
  border-radius: 1rem;
  margin: 5rem auto;
  padding: 2rem;
  display: flex;
  width: 1000px;
  height: 100%;
}
.text-center {
  text-align: center;
  margin: auto;
}
</style>
