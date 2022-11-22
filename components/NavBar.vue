<template lang="pug">
  v-card( color='white' elevation="0" )
    v-app-bar( app fluid color="white" elevation="0" scroll-target="#scrolling-techniques" )
      nuxt-link( to="/" class="pa-5")
        nuxt-logo
      v-spacer
      nuxt-link( class="navButton ma-3 hover-underline-animation" v-bind:class="{'hover-after':$route.path === '/'}" to="/" ) Home
      nuxt-link( class="navButton ma-3 hover-underline-animation" v-bind:class="{'hover-after':$route.path === '/works'}" to="/works" ) Work
      nuxt-link( class="navButton ma-3 hover-underline-animation" v-bind:class="{'hover-after':$route.path === '/playground'}" to="/playground" ) Playground
      v-btn( icon style="text-decoration: none;" class="ma-n2" href="https://www.instagram.com/" )
        v-icon( small ) mdi-instagram
      v-btn( icon style="text-decoration: none;" class="ml-n2 mr-3" href="https://www.linkedin.com/" )
        v-icon( small ) mdi-linkedin
      //a( style="text-decoration: none;" href="https://www.linkedin.com/" )
      //  v-btn( icon )
      //    v-icon( small ) mdi-linkedin
    //v-sheet( id="scrolling-techniques" class="overflow-hidden" max-height="120" )
    //  v-container( style="height: 100px;" )
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style scoped>
.navButton {
  color: black;
  text-decoration: none;
  font-size:13px;
  font-family: 'Alice', serif;
  font-weight: 500;
}

.v-btn i:hover{
  transform: scale(1.25);
}

.hover-underline-animation {
  display: inline-block;
  position: relative;
}

.hover-underline-animation::after{
  content: '';
  position: absolute;
  width: 100%;
  transform: scaleX(0);
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: black;
  transform-origin: bottom right;
  transition: transform 0.25s ease-out;
}

.hover-underline-animation:hover::after {
  transform: scaleX(1);
  transform-origin: bottom left;
}

.hover-after {
  display: inline-block;
  position: relative;
}

.hover-after::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: black;
  transform: scaleX(1);
}
</style>
