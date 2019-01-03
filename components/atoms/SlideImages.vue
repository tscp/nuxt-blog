<template>
  <div :class="pageClass">
    <ul>
      <li v-for="img of slideImages"><img :src="'/assets/images/' + img" /></li>
    </ul>
  </div>
</template>

<script>
  export default {
    props: ['pageClass', 'slideImages'],
    mounted: function() {
      let imgs = this.$el.querySelectorAll('img');
      imgs.forEach(function (el) {
        el.style.opacity = 0;
      });
      this.$nextTick(function() {
        imgs[0].style.opacity = 1;
        let count = 0;
        let before = count - 1;
        clearInterval();

        setInterval(function() {

          count < imgs.length-1 ? count++ : count = 0;
          before = count - 1;
          if(before === -1) {
            before = imgs.length-1;
          }

          (function fadeIn() {
            let val = parseFloat(imgs[count].style.opacity);
            if(!((val += .05) > 1)) {
              imgs[count].style.opacity = val;
              requestAnimationFrame(fadeIn);
            }
          })();

          (function fadeOut() {
            let val = parseFloat(imgs[before].style.opacity);
            if(!((val -= .05) < 0)) {
              imgs[before].style.opacity = val;
              requestAnimationFrame(fadeOut);
            }
          })();

        }, 5000);

      });
    }
  }
</script>

<style lang="scss" scoped>
  ul {
    margin: 0;
    padding: 0;
    position: relative;
    li {
      list-style: none;
      position: absolute;
      img {
        width: 100%;
      }
    }
  }
  .service {
    width: 55%;
    height: 378px;
    ul {
      li {
        width: 605px;
      }
    }
  }
</style>
