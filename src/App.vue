<template>
  <!-- v-if="" (조건식 1==1)-->
  <div class="black-bg" v-if="modalon == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalon = false">닫기</button>
    </div>
  </div>

  <div>
    <div class="menu">
      <!-- v-fro="작명 in 몇번" :key="작명" 반복문 -->
      <a v-for="(a, i) in 메뉴들" :key="i"> {{ a }} </a>
    </div>
  </div>
  <!-- <div v-for="(a, i) in 3" :key="i">
    <h4>{{ products[i] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div> -->

  <div>
    <img :src="원룸들[0].image" class="room-img" alt="" />
    <h4 @click="modalon = true">{{ 원룸들[0].title }}</h4>
    <p>{{ 원룸들[0].price }} 원</p>
    <!-- v-on 약자 @ -->
    <!-- ++ (1을 더해주는 변수), += (숫자마다 더해달라는 변수) -->
    <button @click="increase">허위매물신고</button>
    <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img" alt="" />
    <h4>{{ products[1] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="increase1">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img" alt="" />
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="increase2">허위매물신고</button>
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";
// state
export default {
  name: "App",
  components: {},
  // 데이터 변수 보관함
  data() {
    return {
      메뉴들: ["Home", "About", "Contact"],
      price1: 80,
      price2: 70,
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      원룸들: data,
      신고수: [0, 0, 0],
      modalon: false,
    };
  },
  // 함수 공간
  methods: {
    increase() {
      this.신고수[0]++;
    },
    increase1() {
      this.신고수[1]++;
    },
    increase2() {
      this.신고수[2]++;
    },
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
.room-img {
  width: 100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background: darkblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
