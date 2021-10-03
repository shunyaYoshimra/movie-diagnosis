<template>
  <div>
    <h1 id="title">Q. ジャンルを選びますか？</h1>
    <div id="question1">
      <div class="button first">はい</div>
      <div class="button second">いいえ</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
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
#question1 {
  display: flex;
  justify-content: center;
  margin-top: 180px;
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
</style>