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
            <a href="https://pnrm.co.jp/contact/">Mail form here</a>
          </address>
        </section>
        <section class="foot-info-item sitemap">
          <h4 class="foot-info-title">SITE MAP</h4>
          <div class="foot-info-summary">
            <nav>
              <ul class="foot-nav">
                <li><a href="https://pnrm.co.jp/works/">WORKS</a></li>
                <li><a href="https://pnrm.co.jp/about/">ABOUT</a></li>
                <li><a href="https://pnrm.co.jp/service/">SERVICE</a></li>
                <li><a href="https://pnrm.co.jp/recruit/">RECRUIT</a></li>
                <li><a href="https://pnrm.co.jp/news/">NEWS</a></li>
                <li><a href="https://pnrm.co.jp/contact/">CONTACT</a></li>
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
      width: 100%;
      position: relative;

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

      nav {
        height: 100%;
        margin: 0 auto;
      }

      ul {
        overflow: hidden;
        display: flex;
        flex: 1;
        align-items: center;
        margin: 0;
        padding: 0;
        height: 100%;
        justify-content: space-between;

        li {
          list-style: none;

          a {
            color: #fff;
            text-decoration: none;
          }
        }
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
