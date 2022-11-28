<template>
  <div>
    <img :src="imgUrl" alt="copertina">
    <h1 class="titolo">{{titolo}}</h1>
    <p class="autore">{{autore}}</p>
    <p class="anno">{{anno}}</p>
  </div>
</template>

<script>

export default {
  name: 'cardPage',
  props: {
    imgUrl: String,
    titolo: String,
    autore: String,
    anno: String,
  },
};
</script>

<style lang="scss" scoped>
div{
  background-color: #2E3A46;
  padding: 1rem;
  flex: 0 0 18%;
  text-align: center;
  img{
    width: 100%;
  }
  p{
    color: gray;
    margin: .5rem;
  }
}
</style>
