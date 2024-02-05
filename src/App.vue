<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="black-bg" v-if="isModal == true" @click="isModal = false">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>
  <div class="menu">
    <a v-for="(menu, idx) in menues" :key="idx">{{ menu }}</a>
  </div>
  <div>
    <img src="./assets//해달.jpg" class="room-img" />
    <h4 @click="isModal = true">{{ products[0] }}</h4>
    <p>50만원</p>
    <button @click="reportCnt[0]++">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt[0] }}</spam>
  </div>
  <div>
    <img src="./assets/해달.jpg" class="room-img" />
    <h4 @click="isModal = true">{{ products[1] }}</h4>
    <p>50만원</p>
    <button @click="reportCnt[1]++">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt[1] }}</spam>
  </div>
  <div>
    <img src="./assets/해달.jpg" class="room-img" />
    <h4 @click="isModal = true">{{ products[2] }}</h4>
    <p>50만원</p>
    <button @click="reportCnt[2]++">허위매물 신고 버튼</button
    ><spam>신고 수: {{ reportCnt[2] }}</spam>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
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
