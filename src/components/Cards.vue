<template>
  <div class="container">
    <div class="row">
      <div v-for="item in dataNasaProps" :key="item.id" class="col-4 p-2">
        <div class="card">
          <img :src="item.img_src" class="card-img-top" alt="item.id" />
          <div class="card-body">
            <h5 class="card-title">ID: {{ item.id }}</h5>
            <p class="card-text">Earth Date: {{ item.earth_date }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Cards",
  props: {
    dataNasaProps: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
.card-img-top {
  height: 200px;
}
</style>
