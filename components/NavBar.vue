<template lang="pug">
  v-app-bar( app fluid ref="navBar" v-scroll="getHeight" color="white" elevation=0 prominent shrink-on-scroll )
    nuxt-link( to="/" class="pa-3")
      nuxt-logo
    v-spacer
    div( :class="{'navButtonGroupShrunk':this.height < 57}" )
      nuxt-link(
        class="navButton hover-underline-animation"
        :class="{'hover-after':$route.path === '/', 'navButtonShrunk':this.height < 57, 'mx-4':this.height < 57, 'ma-3':this.height >=57}" to="/"
        @click.native="resetHeight($route.path)"
      ) Home
      nuxt-link(
        class="navButton hover-underline-animation"
        :class="{'hover-after':$route.path === '/works', 'navButtonShrunk':this.height < 57, 'mx-4':this.height < 57, 'ma-3':this.height >=57 }" to="/works"
        @click.native="resetHeight"
      ) Work
      nuxt-link(
        class="navButton hover-underline-animation"
        :class="{'hover-after':$route.path === '/playground', 'navButtonShrunk':this.height < 57, 'mx-4':this.height < 57, 'ma-3':this.height >=57}" to="/playground"
        @click.native="resetHeight"
      ) Playground
    v-btn( icon class="navButton ml-n2 mr-n2" href="https://www.instagram.com/ikkkkyui/" )
      v-icon( :size="this.height < 57 ? 16 : 20" ) mdi-instagram
    v-btn( icon class="navButton ml-n2 mr-3" href="https://www.linkedin.com/in/yutian-yuki-liu/" )
      v-icon( :size="this.height < 57 ? 16 : 20" ) mdi-linkedin
</template>

<script>
export default {
  name: 'NavBar',
  data: () => ({
    height: 9999,
  }),
  methods: {
    getHeight () {
      this.height = this.height === 9999 && this.$route.path !== '/' ? this.height : this.$refs.navBar.computedHeight
    },
    resetHeight () {
      this.height = 9999
    }
  }
}
</script>

<style scoped>
.navButtonGroupShrunk1 {
  padding-left: 5px;
  padding-right: 10px;
}

.navButton {
  color: black;
  text-decoration: none;
  font-family: 'Alice', serif;
  font-weight: 500;
  font-size:16px;
}

.navButtonShrunk {
  font-size: 13px;
  margin-top: 14px;
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
