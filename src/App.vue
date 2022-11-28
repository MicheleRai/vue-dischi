<template>
  <body>
    <headerPage />
    <mainPage />
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

<style lang="scss" scoped>

</style>
