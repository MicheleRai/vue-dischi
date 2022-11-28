<template>
  <main>
    <div class="card-container" v-if="arrDischi">
      <cardPage
        v-for="disco in arrDischi"
        :key="disco.id"
        :imgUrl="disco.poster"
        :titolo="disco.title"
        :autore="disco.author"
        :anno="disco.year"
      >
      </cardPage>
    </div>
    <div v-else>Loading...</div>
  </main>
</template>

<script>
import axios from 'axios';
import cardPage from './cardPage.vue';

export default {
  components: {
    cardPage,
  },
  name: 'mainPage',
  data() {
    return {
      arrDischi: null,
      urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrDischi = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
  main{
    display: flex;
    justify-content: center;
    .card-container{
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      margin: auto;
      margin-top: 3rem;
      max-width: 1200px;
    }
  }
</style>
