<template>
  <DrawingModal
    v-if="showModal"
    @close="showModal = false"
    v-bind:select="result === 0 ? first : second"
  />
  <div class="main">
    <div class="content">
      <h1>제비뽑기</h1>
      <div class="input-box">
        <input
          v-model="first"
          type="text"
          placeholder="1번째 항목을 입력해주세요"
        />
        <input
          v-model="second"
          type="text"
          placeholder="2번째 항목을 입력해주세요"
        />
        <button v-on:click="verify()">Draw</button>
      </div>
    </div>
  </div>
</template>

<script>
import DrawingModal from "./DrawingModal.vue";

export default {
  name: "MainPage",
  components: {
    DrawingModal,
  },
  data() {
    return {
      first: "",
      second: "",
      showResult: false,
      showModal: false,
      result: Math.round(Math.random()),
    };
  },
  methods: {
    verify() {
      if (this.first === "" || this.second === "") {
        return alert("빈 값은 안되죠!");
      }
      this.result = Math.round(Math.random());
      this.showModal = true;
    },
  },
};
</script>

<style scoped>
.main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-content: center;
}

.content {
  width: 500px;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1 {
  color: white;
}

.input-box {
  width: 100%;
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  width: 100%;
  height: 50px;
  margin: 10px 0;
  border-radius: 20px;
  border: 3px solid #000000;
  padding: 0 20px;
}

button {
  width: 100px;
  height: 50px;
  border-radius: 20px;
  border: 3px solid #000000;
  cursor: pointer;
}

button:hover {
  background: lightgreen;
  transition: background 0.3s;
}
</style>
