<template>
  <div>
    <h2>
      <span>OUR MISSION</span>
      MAKE BRAND-NEW EXPERIENCE
    </h2>
    <p>
      panoramaは、デジタル領域を軸とするクリエイティブカンパニーです。<br>
      私たちは、常に広い視野でモノコトに向き合い、<br>
      クリエイティブを通じて、その価値を最大化することで、<br>
      世の中がちょっと良くなる体験を届けます。
    </p>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
  div {
    background-color: #efefef;
    text-align: center;
    color: #000;
    height: 784px;
    padding-top: 150px;
    h2 {
      font-family: "Ropa Sans", sans-serif;
      font-size: 6rem;
      font-weight: normal;
      line-height: 1.2;
      letter-spacing: 0.08em;
      margin: 0 auto 48px;
      span {
        font-size: 36.6%;
        display: block;
        margin-bottom: .5em;
        padding-bottom: 1em;
        position: relative;
        &::before {
          border-bottom: 2px solid #000;
          content: "";
          position: absolute;
          width: 2.5em;
          bottom: 0;
          left: 50%;
          transform: translateX(-50%);
        }
      }
    }
    p {
      font-size: 1.8rem;
      line-height: 1.9;
    }
  }
</style>
