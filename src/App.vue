<template>
  <div class="main">
    <div class="wrap">
      <h1>Review</h1>
      <textarea v-model="review" class="input"></textarea>
      <button @click="onClickHandler" class="btn">Kirim</button>

      <div v-for="(text, index) in reviews" :key="index" class="review">
        
        <span><i class='bx bxs-user'></i> {nama pengguna}</span>
        <h1>" {{ text }} "</h1>
        <p>{timestamps}</p>
        <br>
        <button @click="onDelete(index)"><i class='bx bxs-trash' ></i></button>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      review: '',
      reviews: []
    }
  },
  methods: {
    onClickHandler() {
      this.reviews.push(this.review)
    },
    onDelete(index) {
      this.reviews.splice(index, 1);
    },
  }
}
</script>

<style scoped>
* {
  font-family: 'poppins', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.main {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  background-color: #eee;
}

button {
  cursor: pointer;
  width: 0%;
  background: transparent;
  border: none;
  color: red;
}

button i {
  width: 50%;
}
.wrap {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

h1 {
  margin: 12px 0;
  font-size: 1.15rem;
  font-weight: 600;
}

.input {
  height: 75px;
  width: 465px;
  background-color: #ffffff;
}

.btn {
  height: 40px;
  width: 80px;
  background-color: #00d70b;
  color: white;
  font-size: 1.05rem;
  margin-top: 10px;
  border-radius: 5px;
  border-style: none;
  cursor: pointer;
}

.review {
  height: 100%;
  width: 465px;
  display: flex;
  /* align-items: center; */
  flex-direction: column;
  padding: 20px;
  background-color: #ffffff;
  border-radius: 5px;
  margin: 10px 0;
  word-break: break-all;
}
</style>
