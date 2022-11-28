<template>
  <body>
    <headerPage />
    <mainPage>
      <cardPage />
    </mainPage>
  </body>
</template>

<script>
import headerPage from '@/components/headerPage.vue';
import mainPage from '@/components/mainPage.vue';

export default {
  components: {
    headerPage,
    mainPage,
  },
};
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: white;
  }
  body{
    background-color: #1E2D3B;
  }
</style>
