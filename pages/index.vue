<template lang="pug">
  v-container( fluid )
    v-row( justify="center" align="center" )
      v-img( :src="require(`@/static/images/peeps-avatar-alpha.png`)" max-width="500" )
    v-row
      v-card( height="50" )
    v-row( justify="center" )
      //v-btn( icon :to="{ path: '/', hash:'#profile-section'}" )
      v-btn( elevation="0" class="jump-arrow" @click="$vuetify.goTo('#profile-section', {duration: 0.1})" )
        v-icon( size="50px" ) mdi-chevron-down
    v-row
      v-card( height="100" )
    v-row
      v-card( id="profile-section" height="100" )
    v-row
      v-container( fluid style="background:white;" )
        v-row( max-width class="py-5" align="center")
          v-col( cols="3" )
          v-col( cols="4" )
            h1( style={color: "title"} ) Yuki Liu
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            p Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            v-sheet( height="20" )
            v-btn( outlined color="buttonPrimary" ) Download Resume
          v-col( cols="2" align="right")
            v-avatar( size=200 )
              v-img( :src="require(`@/static/images/yuki1.jpg`)" )
          v-col( cols="3" )
    v-row
      v-card( height="200" )
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'Home'
})
</script>

<style scoped>
h1 {
  color: var(--v-title-base, back) !important;
}
.jump-arrow {
  background-color: transparent !important;
}
</style>
