<template>
  <div id="app" :style="appBackground">
    <h2>MASUKKAN 12 HURUF UNTUK MERUBAH BACKGROUND </h2>
    <div class="input-container">
      <input type="text" v-model="inputText" @input="checkInputLength" placeholder="Ketik sesuatu...">
    </div>
    <div class="message-container">
      <p v-if="inputText.length >= 12" class="message">Masukan Anda telah mencapai 12 karakter!</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      inputText: '',
      appBackground: {
        backgroundColor: "blue",
      }
    };
  },
  created() {
    document.body.style.backgroundColor = "red";
    
  },
  methods: {
    checkInputLength() {
      if (this.inputText.length >= 12) {
        this.appBackground.backgroundColor = "orange";
      } else {
        this.appBackground.backgroundColor = "blue";
      }
    }
  }
};
</script>

<style scoped>
#app {
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.input-container {
  margin-bottom: 20px;
}

input {
  padding: 10px;
  border: 2px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

.message-container {
  margin-top: 20px;
}

.message {
  color: #ffffff;
  font-size: 18px;
}
</style>
