<template>
  <div>
    <div class="black-bg" @click="modal = false" v-if="modal === true">
      <div class="white-bg">
        <h4>상세 페이지 입니다</h4>
        <p>
          상세 페이지 내용입니다
          <button @click="modal = false">닫기</button>
        </p>
      </div>
    </div>

    <div class="menu">
      <a v-for="(작명, index) in menus" v-bind:key="index">{{ 작명 }}</a>
    </div>

    <div v-for="(el, index) in products" v-bind:key="index">
      <img @click="modal = true" class="room-img" :src="el.image" />
      <h4>{{ el.title }}</h4>
      <p>{{ el.price }}</p>
      <p>{{ el.content }}</p>
      <button @click="report1++">허위 매물 신고</button>
      <span> 신고수: {{ report1 }}</span>
    </div>
  </div>
</template>

<script>
import room from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
      modal: false,
      report1: 0,
      report2: 0,
      report3: 0,
      menus: ["home", "shop", "about"],
      products: room,
    };
  },
  methods: {},

  components: {},
};
</script>

<style>
.room-img {
  width: 50%;
  margin-top: 40px;
}

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
  padding: 10px;
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
  padding: 10px;
}
</style>
