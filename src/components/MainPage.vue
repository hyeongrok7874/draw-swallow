<template>
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
        <button v-on:click="showResult = !showResult">Draw</button>
        <div v-if="showResult && result === 0">
          {{ first }}
        </div>
        <div v-if="showResult && result === 1">
          {{ second }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainPage",
  data() {
    return {
      first: "",
      second: "",
      showResult: false,
      result: Math.floor(Math.random() * 2),
    };
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
