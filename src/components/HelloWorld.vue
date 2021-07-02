<template>
  <div>
    <h1 class="mb-5">오늘의 벚꽃</h1>
    <button type="button" class="btn btn-dark mb-5" @click="getPlace">어디로 갈까요?</button>
    <br>
    <div v-if="isShow" class="d-flex justify-content-center mb-5">
      <div class="card" style="width: 30rem;">
        <img :src="imgSrc" class="card-img-top" alt="">
        <div class="card-body">
          <p class="card-text">{{ place }}</p>
        </div>
      </div>
    </div>
    <div id="sound">
      <!-- <iframe src="../assets//silence.mp3" allow="autoplay" id="audio" style="display:none"></iframe> -->
      <!-- <audio autoplay loop controls>
        <source src="../assets/장범준-01-흔들리는꽃들속에서네샴푸향이느껴진거야.mp3" type="audio/mp3">
      </audio> -->
    </div>
  </div>
</template>

<script>
import _ from 'lodash'

export default {
  name: "HelloWorld",
  data: function () {
    return {
      places: ['여의도', '석촌호수', '남산', '서울숲', '현충원', '어린이대공원'],
      place: '',
      imgSrc: '',
      isShow: false,
    }
  },
  methods: {
    getPlace: function () {
      this.place = _.sample(this.places)
      this.imgSrc = require(`../assets/${this.place}.jpg`)
      this.isShow = true
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @font-face {
      font-family: 'yg-jalnan';
      src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_four@1.2/JalnanOTF00.woff') format('woff');
      font-weight: normal;
      font-style: normal;
  }

  * {
    font-family: 'yg-jalnan';
  }

  /* img {
    width: 40%;
  } */

  h1 {
    color: #F5A9D0;
    font-size: 60px;
  }

  button {
    background-color: #F5A9D0;
    border-color: #F5A9D0;
  }

  p {
    font-size: 25px;
  }

  .btn-dark:hover {
    color: #fff;
    background-color: #F5A9D0;
    border-color: #F5A9D0;
  }

  .btn-check:focus+.btn-dark, .btn-dark:focus {
    color: #fff;
    background-color: #F5A9D0;
    border-color: #F5A9D0;
    box-shadow: 0 0 0 0rem rgb(66 70 73 / 50%);
}
</style>
