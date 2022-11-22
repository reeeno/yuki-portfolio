<template lang="pug">
  v-container
    v-row( justify="center" align="center" )
      nuxt-img( src="/images/snow.png" width="250"  id="cloud" @click="snowing = !snowing" )
    div( v-show="snowing" class="snowflakes" aria-hidden="true" )
      div( class="snowflake" ) ❅
      div( class="snowflake" ) ●
      div( class="snowflake" ) .
      div( class="snowflake" ) ❆
      div( class="snowflake" ) ●
      div( class="snowflake" ) ❅
      div( class="snowflake" ) ❅
      div( class="snowflake" ) ●
      div( class="snowflake" ) ❆
      div( class="snowflake" ) ●
      div( class="snowflake" ) ❅
      div( class="snowflake" ) ❆
</template>

<script>
export default {
  name: 'Snow',
  data: () => {
    return {
      snowing: false
    }
  },
  methods: {}
}
</script>

<style scoped>
@import '~/assets/style/snow.css';
</style>
