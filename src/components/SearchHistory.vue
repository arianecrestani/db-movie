<template>
  <div class=" bg-gray-100 w-2/4  list-none cursor-default">
    <ul  v-for="(item, index) in searchHistory" v-bind:key="index">
      <li class="hover:bg-green-700 p-3" @click="setResult(item)">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SearchHistory",
  methods: {
    setResult(item) {
      this.$emit("valueselected", item);
    },
  },
  computed: {
    searchHistory: function() {
      const searchHistory = this.$store.state.searchHistory
      return searchHistory.reverse().slice(0,4)
      
    },
  },
};
</script>

<style></style>
