<template lang="pug">
  v-container( fluid )
    v-row( justify="center" align="center" )
      v-img( :src="require(`@/static/images/peeps-avatar-alpha.png`)" max-width="600" )
    v-row
      v-sheet( height="100" )
    v-row( justify="center" )
      v-btn( elevation="0" class="jump-arrow" @click="$vuetify.goTo('#profile-section', {duration: 300})" )
        v-icon( size="50px" ) mdi-chevron-down
    v-row
      v-sheet( height="50" )
    v-row
      v-sheet( id="profile-section" height="100" )
    v-row
      v-container( fluid style="background:white;" )
        v-sheet( height="60" )
        v-row( max-width align="center")
          v-col( cols="3" )
          v-col( cols="3" )
            h1( style={color: "title"}) Yuki Liu
            p( class="p2" ) Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            p( class="p2" ) Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            v-sheet( height="20" )
            v-btn( class="primaryButton" outlined color="buttonPrimary" ) Download Resume
          v-col( cols="1" )
          v-col( cols="2" align="right")
            v-avatar( size=300 )
              v-img( :src="require(`@/static/images/yuki1.jpg`)" )
          v-col( cols="3" )
        v-sheet( height="80" )
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

.v-btn {
  border-width: 2px;
}
</style>
