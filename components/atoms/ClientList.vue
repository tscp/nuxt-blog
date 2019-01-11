<template>
  <div>
    <dl>
      <dt>{{ category }}</dt>
      <dd>
        <ul>
          <li v-for="li of list">{{ li }}</li>
        </ul>
      </dd>
    </dl>
  </div>
</template>

<script>
  export default {
    props: ['category','list']
  }
</script>

<style lang="scss" scoped>
  dl {
    display: flex;
  }
  dt {
    width: 25%;
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-size: 1.5rem;
    text-decoration: none;
    letter-spacing: 0.05em;
    line-height: 1.5;
  }
  dd {
    font-size: 1.2rem;
    width: 75%;
  }
  ul {
    display: flex;
    flex-wrap: wrap;
  }
  li {
    width: 33.33333%;
    margin: 0 0 19px;
    color: #868686;
    line-height: 1.6;
    list-style: none;
  }
</style>
