<template>
  <header>
    <Logo class="logo"/>
    <nav>
      <ul>
        <li><a href="/works/">WORKS</a></li>
        <li><a href="/service/">SERVICE</a></li>
        <li><a href="/news/">NEWS</a></li>
        <li><a href="/about/">ABOUT</a></li>
        <li><a href="/recruit/">RECRUIT</a></li>
        <li><a href="/contact/">CONTACT</a></li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>

  @media(min-width: 769px) {
    header {
      background-color: rgba(0, 0, 0, 0.12);
      width: 100%;
      height: 90px;
      position: fixed;
      top: 0;
      left: 0;
      z-index: 999;

      &:hover {
        background-color: #000;
        background-color: rgba(0, 0, 0, 0.8);
        transition: 0.2s ease;

        /deep/ .logo svg {
          fill: #fff;
        }
      }

      nav {
        width: 476px;
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
            font-family: "Ropa Sans", sans-serif;
            letter-spacing: 1px;
            text-decoration: none;
          }
        }
      }
    }
  }
</style>

<script>
  import Logo from '~/components/atoms/Logo.vue'
  export default {
    components: {
      Logo
    }
  }
</script>
