<template>
  <div id="app">
    <h2> FRUITS VOCABULARY </h2>
    <input type="text" v-model="search">
    <div v-for="post in filteredSearch" :key="post.id">
      <SearchContent :post="post"/>
    </div>
  </div>
</template>

<script>
import SearchContent from "./components/SearchContent";

export default {
  name: "App",
  components: {
    SearchContent
  },
  data() {
    return {
      search: "",
      searchcontent: [
        {
          id: 1,
          text: "Tomato: Tomato is known as the most popular fruit in the world."
        },
        {
          id: 2,
          text: "Avocado: The fruit I love to eat at breakfast is the avocado."
        },
        {
          id: 3,
          text: "Eggplant: My brother does not like foods made with eggplant."
        },
        {
          id: 4,
          text: "Olives: In our house, olives are the most indispensable food for breakfast."
        },
        {
          id: 5,
          text: "Wheat: The warm breads we eat every morning at breakfast are made from wheat flour."
        },
        {
          id: 6,
          text: "Corn: I love eating corn while watching movies in the cinema."
        },
        {
          id: 7,
          text: "Cucumber: I love eating cucumber, but I also use it to make my skin beautiful."
        },
        {
          id: 8,
          text: "Pumpkin: A variety of decorative products are made from pumpkin at Halloween."
        },
        {
          id: 9,
          text: "Pepper: My father collected the peppers he had grown in our garden in the village today, they were all very fresh and delicious."
        },
        {
          id: 10,
          text: "Banana: Banana is known worldwide as a radioactive fruit."
        },
        {
          id: 11,
          text: "Squash: I love squash food, but my father doesn’t like it at all."
        }
      ]
    };
  },
  computed: {
    filteredSearch() {
      return this.searchcontent.filter(content =>
        content.text.toLowerCase().includes(this.search.toLowerCase())
      );
    }
  }
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
