<template>
  <div>
    <Header />
    <nuxt/>
    <Footer />
  </div>
</template>

<script>
  import Header from '~/components/Header'
  import Footer from '~/components/Footer'
  export default {
    components : {
      Header, Footer
    }
  }
</script>

<style lang="scss">
  html {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "游ゴシック", "Yu Gothic", "游ゴシック体", "YuGothic", YuGothic, "ヒラギノ角ゴ ProN W3", "Hiragino Kaku Gothic ProN", "Hiragino Kaku Gothic Pro", Meiryo, メイリオ, Roboto, "MS PGothic", "ＭＳ Ｐゴシック", sans-serif;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }
  body {
    font-size: 1.6em;
  }

  *, *:before, *:after {
    box-sizing: border-box;
    margin: 0;
  }

  :root {
    box-sizing: border-box;
    font: 62.5% / 1.5 sans-serif;
    text-rendering: optimizeLegibility;
  }
</style>
