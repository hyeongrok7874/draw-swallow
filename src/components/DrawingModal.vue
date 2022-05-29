<template>
  <div class="main">
    <div class="content">
      <transition name="fade" appear>
        <img v-if="viewSwallow" src="/swallow.png" />
      </transition>
      <p class="desc">제비의 선택은?</p>
      <p class="result">{{ select }}</p>
      <button @click="$emit('close')">확인</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "DrawingModal",
  props: {
    select: String,
  },
  data() {
    return {
      viewSwallow: true,
    };
  },
  methods: {
    showSwallow() {
      setTimeout(() => {
        this.viewSwallow = false;
      }, 1000);
    },
  },
  mounted() {
    this.showSwallow();
  },
};
</script>

<style scoped>
.main {
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.51);
  display: flex;
  justify-content: center;
  align-items: center;
}
.content {
  width: 700px;
  height: 700px;
  background: white;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  border-radius: 20px;
  position: relative;
}
.desc {
  font-size: 40px;
}
.result {
  font-size: 50px;
  font-weight: 900;
  color: purple;
}
@keyframes fadeOut {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
img {
  width: 100%;
  height: 100%;
  position: absolute;
  background: white;
}
button {
  width: 200px;
  height: 50px;
  border-radius: 30px;
  cursor: pointer;
  background: white;
  font-size: 20px;
}
button:hover {
  background: lightgreen;
  transition: background 0.3s;
}

.fade-leave-active {
  transition: opacity 1s ease-out;
}

.fade-leave-to {
  opacity: 0;
}
</style>
