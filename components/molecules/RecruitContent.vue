<template>
  <div class="recruit-content">
    <article>
      <RecruitTitle :name="name" :sub="sub"/>
      <RecruitDescription :description="description" />
      <EntryButton :url="url" />
    </article>
  </div>
</template>

<script>
  import RecruitTitle from '~/components/atoms/RecruitTitle'
  import RecruitDescription from '~/components/atoms/RecruitDescription'
  import EntryButton from '~/components/atoms/EntryButton'
  export default {
    props: ['name', 'sub', 'description', 'url'],
    components: {
      RecruitTitle, RecruitDescription, EntryButton
    }
  }
</script>

<style lang="scss" scoped>
  .recruit-content {
    article {
      width: 864px;
      padding: 86px 0;
      margin: 0 auto;
      &:first-child {
        padding-top: 0;
      }
      /deep/ div dl:first-child {
        margin-top: 0;
      }
    }
  }
</style>
