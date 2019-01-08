<template>
  <div class="tab">
    <ul class="tab-content">
      <li><TabButton en="DIRECTOR" ja="ディレクター中途採用" /></li>
      <li><TabButton en="DESIGNER" ja="デザイナー中途採用" /></li>
      <li><TabButton en="OPERATOR" ja="運用スタッフ中途採用" /></li>
      <li><TabButton en="ASSISTANT" ja="インターン・アシスタント採用" /></li>
    </ul>
  </div>
</template>

<script>
  import TabButton from '~/components/atoms/TabButton'
  export default {
    components: {
      TabButton
    }
  }
</script>

<style lang="scss" scoped>
  div {
    background-color: #f6f5f6;
    padding: 48px 0;

    .tab-content {
      width: 95%;
      display: flex;
      margin: 0 auto;
      border-right: 1px solid #e8e8e8;
      padding: 0;

      li {
        border-left: 1px solid #e8e8e8;
        line-height: 1;
        list-style: none;
        width: 25%;
        color: #7f7f7f;
        fill: #7f7f7f;
        transition: all 0.4s;
        position: relative;

        .active {
          opacity: 1;
          z-index: 2;
        }

        &::after {
          content: '';
          display: block;
          width: 0;
          height: 0;
          border-style: solid;
          border-width: 8px 4px 0 4px;
          border-color: #7f7f7f transparent transparent transparent;
          transition: all 0.4s;
          transform: translate3d(-4px, -12px, 0);
          position: absolute;
          left: 50%;
        }

        &.active, &:hover {
          color: #000;
          fill: #000;

          &::after {
            border-color: #000 transparent transparent transparent;
          }
        }
      }
    }
  }
</style>
