<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="black-bg" v-if="isModal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="isModal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, idx) in menues" :key="idx">{{ menu }}</a>
  </div>

  <div v-for="(oneroom, idx) in onerooms" :key="idx">
    <img :src="oneroom.image" class="room-img" />
    <h4 @click="isModal = true">{{ oneroom.title }}</h4>
    <p>{{ oneroom.price }}만원</p>
  </div>
</template>

<script>
import data from "./assets/data";

export default {
  name: "App",
  data() {
    return {
      onerooms: data,
      isModal: false,
      reportCnt: [0, 0, 0],
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
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

div h4 {
  cursor: pointer;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
