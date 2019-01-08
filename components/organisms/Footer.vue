<template>
  <footer>
    <div class="inner">
      <PageTopButton />
      <div class="foot-info-list">
        <section class="foot-info-item here">
          <h4>WE ARE HERE</h4>
          <address>
            <span class="ja">〒150-0034<br>東京都渋谷区代官山町9-10 Sodacco 3F<br>
            <span class="en">Sodacco 3F, 9-10 Daikanyama-cho, Shibuya-ku, Tokyo</span></span>
          </address>
        </section>
        <section class="foot-info-item contact">
          <h4>CONTACT US</h4>
          <address>
            <span class="tel">TEL : 03-6455-1030</span>
            <span class="fax">FAX : 03-6455-1031</span><br> →
            <a href="/contact">Mail form here</a>
          </address>
        </section>
        <section class="foot-info-item sitemap">
          <h4>SITE MAP</h4>
          <div class="foot-info-summary">
            <nav>
              <ul class="foot-nav">
                <li><a href="/works">WORKS</a></li>
                <li><a href="/about">ABOUT</a></li>
                <li><a href="/service">SERVICE</a></li>
                <li><a href="/recruit">RECRUIT</a></li>
                <li><a href="/news">NEWS</a></li>
                <li><a href="/contact">CONTACT</a></li>
              </ul>
            </nav>
          </div>
        </section>
      </div>
      <div class="foot-bottom">
        <small class="foot-bottom__item copyright">&copy; Panorama Inc.</small></div>
    </div>
  </footer>
</template>

<style lang="scss">

  @media(min-width: 769px) {
    footer {
      background-color: #000;
      font-family: "Roboto", sans-serif;
      width: 100%;
      position: relative;
      padding: 30px 40px 70px;

      .foot-info-list {
        display: table;
        width: 100%;
        border-top: 1px solid #282828;
        border-bottom: 1px solid #282828;
      }

      .foot-info-item {
        display: table-cell;
        width: 33.33%;
        padding: 2% 1%;
        vertical-align: top;
      }

      h4 {
        color: #fff;
        font-size: 1.8rem;
        margin-bottom: 1em;
        font-family: "Ropa Sans", sans-serif;
        font-weight: normal;
        letter-spacing: .1em;
      }

      address {
        color: #fff;
        font-size: 1.2rem;
        font-style: normal;
        font-family: "Roboto", sans-serif;
        font-weight: normal;
        line-height: 2;
        letter-spacing: .1em;
        a {
          color: #fff;
        }
        .ja {
          font-family: "游ゴシック", "Yu Gothic", "游ゴシック体", "YuGothic", YuGothic, "ヒラギノ角ゴ ProN W3", "Hiragino Kaku Gothic ProN", "Hiragino Kaku Gothic Pro", Meiryo, メイリオ, Roboto, "MS PGothic", "ＭＳ Ｐゴシック", sans-serif;
          font-weight: normal;
          letter-spacing: 0;
        }
        .en {
          color: #919191;
        }
        .tel {
          display: inline-block;
          padding-right: 30px;
        }
      }

      nav {
        font-size: 1.2rem;
        font-style: normal;
        font-family: "Roboto", sans-serif;
        font-weight: normal;
        height: 100%;
        margin: 0 auto;
      }

      ul {
        overflow: hidden;
        display: flex;
        flex: 1;
        flex-wrap: wrap;
        align-items: center;
        margin: 0;
        padding: 0;
        height: 100%;
        justify-content: space-between;
        width: 350px;

        li {
          display: inline-block;
          list-style: none;
          line-height: 2;
          width: 105px;

          &:before {
            content: "・";
            color: #fff;
            margin-right: 4px;
          }

          a {
            color: #fff;
            letter-spacing: 1px;
            text-decoration: none;
            transition: color 0.4s;
            &:hover {
              color: #45adcc;
            }
          }
        }
      }

      .foot-bottom {
        display: table;
        width: 100%;
        padding: 30px 1% 0;
      }
      .copyright {
        font-size: 1rem;
        color: #8e8e8e;
        display: table-cell;
        text-align: right;
        vertical-align: bottom;
      }

    }
  }
</style>

<script>
  import PageTopButton from '~/components/atoms/PageTopButton'
  export default {
    components : {
      PageTopButton
    }
  }
</script>
