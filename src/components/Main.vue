<template>
  <div>
    <h1 id="title">{{ titleArray[questionNum] }}</h1>
    <div class="question two-items" v-if="questionNum === 0">
      <div @click="answer1()" class="button first">はい</div>
      <div @click="answer1()" class="button second">いいえ</div>
    </div>
    <div class="question" id="question2" v-if="questionNum === 1">
      <div
        v-for="option in question2Object.options"
        :key="option"
        @click="check2"
        class="button btn-2"
      >
        {{ option }}
      </div>
      <div class="next-button" @click="answer2()">次へ</div>
    </div>
    <div class="question three-items" v-if="questionNum === 2">
      <div @click="answer3()" class="button">有名</div>
      <div @click="answer3()" class="button center">マイナー</div>
      <div @click="answer3()" class="button">どちらも</div>
    </div>
    <div class="question two-items" v-if="questionNum === 3">
      <div @click="answer4()" class="button first">最近</div>
      <div @click="answer4()" class="button second">昔</div>
    </div>
    <div class="question three-items" v-if="questionNum === 4">
      <div @click="answer5()" class="button">洋画</div>
      <div @click="answer5()" class="button center">邦画</div>
      <div @click="answer5()" class="button">どちらも</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questionNum: 0,
      titleArray: [
        "Q. ジャンルを選びますか？",
        "Q. ジャンルを１〜３つ選んでください",
        "Q. 有名なもの？マイナー？",
        "Q. 年代は？",
        "Q. 洋画？邦画？",
        "あなたにオススメの映画7選はこちら！",
      ],
      question2Object: {
        options: [
          "アクション",
          "アドベンチャー",
          "アニメ",
          "SF",
          "音楽",
          "コメディ",
          "サスペンス",
          "スポーツ",
        ],
      },
    };
  },
  methods: {
    answer1() {
      this.questionNum++;
    },
    check2(event) {
      if (event.target.classList.contains("clicked")) {
        event.target.classList.remove("clicked");
      } else {
        event.target.className += " clicked";
      }
    },
    answer2() {
      this.questionNum++;
    },
    answer3() {
      this.questionNum++;
    },
    answer4() {
      this.questionNum++;
    },
    answer5() {
      this.questionNum++;
    },
  },
};
</script>

<style>
#title {
  margin-top: 120px;
  text-align: center;
  color: #babecc;
  font-size: 2rem;
  letter-spacing: 5px;
}
.question {
}
.two-items {
  margin-top: 180px;
  display: flex;
  justify-content: center;
}
#question2 {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 30px;
  width: 70%;
  margin: auto;
  margin-top: 120px;
}
.three-items {
  margin-top: 180px;
  display: flex;
  justify-content: center;
}
.center {
  margin: 0 20px;
}
.button {
  width: 280px;
  height: 80px;
  box-shadow: 4px 4px 8px rgba(189, 195, 199, 0.26),
    2px 2px 4px rgba(255, 255, 255, 0.7) inset;
  border: 1px solid rgba(189, 195, 199, 0.1);
  border-radius: 5px;
  text-align: center;
  line-height: 80px;
  font-size: 1.375rem;
  font-weight: lighter;
  color: #707070;
  cursor: pointer;
}
.btn-2 {
  margin: auto;
}
.button:hover {
  transform: translateY(-5px);
  box-shadow: 8px 8px 16px rgba(189, 195, 199, 0.26),
    4px 4px 8px rgba(255, 255, 255, 0.7) inset;
}
.firest {
  margin-right: 35px;
}
.second {
  margin-left: 35px;
}
.next-button {
  box-shadow: 4px 4px 8px rgba(189, 195, 199, 0.26),
    2px 2px 4px rgba(255, 255, 255, 0.7) inset;
  border: 1px solid rgba(189, 195, 199, 0.1);
  border-radius: 30px;
  width: 120px;
  height: 50px;
  margin: auto;
  line-height: 50px;
  text-align: center;
  color: #3bbbff;
  cursor: pointer;
}
.next-button:hover {
  transform: translateY(-5px);
  box-shadow: 8px 8px 16px rgba(189, 195, 199, 0.26),
    4px 4px 8px rgba(255, 255, 255, 0.7) inset;
}
.clicked {
  box-shadow: none;
}
.clicked:hover {
  transform: none;
  box-shadow: none;
}
</style>