<template>
  <div :class="direction">
    <figure>
      <ul>
        <li><img :src="img1" /></li>
        <li><img :src="img2" /></li>
        <li><img :src="img3" /></li>
      </ul>
      <figcaption>
        <h3>{{ h3 }}</h3>
        <p>{{ p }}</p>
      </figcaption>
    </figure>
  </div>
</template>

<script>
  export default {
    props: ['direction', 'img1', 'img2', 'img3', 'h3', 'p'],
    mounted: function() {
      let imgs = document.querySelectorAll('img');
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
  div {
    width: 86%;
    margin: 0 auto;
  }
  h3 {
    margin-bottom: 30px;
    text-align: left;
    font-size: 1.6rem;
    font-weight: bold;
    line-height: 1.5;
  }
  p {
    font-size: 1.2rem;
    line-height: 1.9;
  }
  ul {
    margin: 0;
    padding: 0;
    position: relative;
    li {
      list-style: none;
      width: 605px;
      position: absolute;
      img {
        width: 100%;
      }
    }
  }
  figure {
    display: flex;
    justify-content: space-between;
    min-height: 415px;
    figcaption {
      width: 40%;
    }
  }
  .right figure {
    flex-direction: column-reverse;
  }
</style>
