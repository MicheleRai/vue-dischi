<template>
  <div>
   <label for="s">
      <input
        id="s"
        type="text"
        v-model="inputTitle"
        placeholder="cerca"
        @keyup.enter="$emit('search', inputTitle)"
      >
    </label>
  </div>
</template>

<script>
export default {
  name: 'searchBar',
  data() {
    return {
      inputTitle: '',
    };
  },
};
</script>

<style lang="scss" scoped>
  div{
    color: black;
  }

</style>
