<template>
  <main>
    <search-bar class="barcontainer" @search="searchTitle"/>
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
import searchBar from './searchBar.vue';

export default {
  components: {
    cardPage,
    searchBar,
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

  computed: {
    /* searchTitle() {
      return this.arrDischi.filter((disco) =>
      disco.title.trim().toLowerCase().includes(this.search.trim().toLowerCase()));
    }, */
  },
};
</script>

<style lang="scss" scoped>
  main{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .barcontainer{
      margin-top: 2rem;
      color: black;
    }
    .card-container{
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      margin: auto;
      margin-top: 2rem;
      max-width: 1200px;
      color: white;
    }
  }
</style>
