<template>
  <div class="service-tab-button" v-on:click="handler">
    <i class="service-tab-icon" v-if="icon === 'research'">
      <IconResearch />
    </i>
    <i class="service-tab-icon" v-else-if="icon === 'planning'">
      <IconPlanning />
    </i>
    <i class="service-tab-icon" v-else-if="icon === 'solution'">
      <IconSolution />
    </i>
    <i class="service-tab-icon" v-else-if="icon === 'operation'">
      <IconOperation />
    </i>
    <p class="service-title-en">{{ en }}</p>
    <p class="service-title-ja">{{ ja }}</p>
  </div>
</template>

<script>
  import IconResearch from '~/components/atoms/IconResearch'
  import IconPlanning from '~/components/atoms/IconPlanning'
  import IconSolution from '~/components/atoms/IconSolution'
  import IconOperation from '~/components/atoms/IconOperation'

  export default {
    props : ['en', 'ja', 'icon'],
    data () {
      return {
        value: 'icon'
      }
    },
    methods : {
      handler: function() {
        let index;
        let tabs = document.querySelector('.tab-content').querySelectorAll('li');
        tabs.forEach(function (el) {
          if(el.classList.contains('active')) {
            el.classList.remove('active');
          }
        });
        let tabVisuals = document.querySelector('.tab-visuals').querySelectorAll('div');
        tabVisuals.forEach(function (el) {
          if(el.classList.contains('active')) {
            el.classList.remove('active');
          }
        });
        this.$el.parentElement.classList.add('active');

        let tab = document.querySelector('.tab-content').getElementsByTagName('li');
        let target = document.querySelector('.tab-content').querySelector('.active');
        tab = [].slice.call(tab);
        index = tab.indexOf(target);
        document.querySelector('.tab-visuals').children[index].classList.add('active');
      }
    },
    components : {
      IconResearch, IconPlanning, IconSolution, IconOperation
    }
  }
</script>

<style lang="scss" scoped>
  .service-tab-button {
    cursor: pointer;
    text-align: center;
    padding: 60px 0 45px;
    box-sizing: border-box;
    line-height: 1;
    i {
      display: block;
      height: 32px;
      margin-bottom: 20px;
    }
  }
  .service-title {
    &-en {
      margin-bottom: 10px;
      font-family: "Roboto Condensed", sans-serif;
      font-weight: 700;
      text-decoration: none;
      letter-spacing: 0.05em;
      font-size: 1.6rem;
    }
    &-ja {
      font-size: 1.1rem;
    }
  }
</style>
