<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="menu">
    <a v-for="(menu, idx) in menues" :key="idx">{{ menu }}</a>
  </div>
  <div v-for="(product, idx) in products" :key="idx">
    <h4>{{ product }}</h4>
    <p>50만원</p>
    <button v-on::click="reportCnt++">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt }}</spam>
    <button v-on::click="increase">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt }}</spam>
    <button @click="reportCnt++">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt }}</spam>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      reportCnt: 0,
      menues: ["Home", "Product", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase() {
      this.reportCnt++;
    },
  },
  components: {
    // HelloWorld
  },
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

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding-left: 10px;
  cursor: pointer;
}
</style>
