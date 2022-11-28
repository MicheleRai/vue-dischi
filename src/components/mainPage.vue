<template>
  <main>main</main>
</template>

<script>
import axios from 'axios';
import { get } from 'http';
import { log } from 'console';

export default {
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
        this.arrDischi = 'risposta api';
      });
  },
};
</script>

<style lang="scss" scoped>
  main{
    display: flex;
    justify-content: center;
    gap: 2rem;

  }
</style>
