<template>
  <nav>
    <div id="router">
      <router-link to="/" class="z" v-if="windowWidth >= 945">Home</router-link>
      <router-link to="/about" class="z" v-if="windowWidth >= 945">About</router-link>
      <router-link to="/sound" class="z" v-if="windowWidth >= 945">Sound</router-link>
      <router-link to="/community" class="z" v-if="windowWidth >= 945">Community</router-link>
      <router-link to="/message" class="z" v-if="windowWidth >= 945">Message</router-link>
      <router-link to="/account" class="z" v-if="windowWidth >= 945">Account</router-link>
      <span v-if="windowWidth < 945" class="z"></span>
    </div>
    <transition id="mobile_router"  v-show="isActive01" v-if="windowWidth < 945">
      <ul>
        <li>
          <router-link to="/" class="y">Home</router-link>
        </li>
        <li>
          <router-link to="/about" class="y">About</router-link>
        </li>
        <li>
          <router-link to="/sound" class="y">Sound</router-link>
        </li>
        <li>
          <router-link to="/community" class="y">Community</router-link>
        </li>
        <li>
          <router-link to="/message" class="y">Message</router-link>
        </li>
        <li>
          <router-link to="/account" class="y">Account</router-link>
        </li>
      </ul>
    </transition>
    <div id="router_view" @click='isActive01     =     !isActive01' v-if="windowWidth < 945">
      <span class="bar b_t"></span>
      <span class="bar b_c"></span>
      <span class="bar b_b"></span>
    </div>
  </nav>
  <div id="a">
    <router-view />
  </div>
</template>

<style>
#router{
  z-index: 500;
  background: #ffffff;
}
.v-enter-to {
  transition: transform 0.5s;
  transform: translateY(0px);
}
.v-enter-from {
  transform: translateY(-200px);
}

.v-leave-to {
  transition: transform 0.5s;
  transform: translateY(-200px);
}
.v-leave-from {
  transform: translateY(0px);
}

ul {
  list-style: none;
}

li {
  margin-top: 10px;
}

.z {
  margin: 0 50px 0 50px;
  height: 60px;
  line-height: 60px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  margin: auto;
  background: #ffffff;
  border-bottom: 1px solid;
  height: 60px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #00b7ff;
}

#a {
  position: absolute;
  z-index: -1;
  top: 80px;
  left: 0;
  right: 0;
  width: 100%;
  margin: auto;
}

.bar {
  position: absolute;
  left: 0;
  right: 0;
  margin: auto;
  width: 30px;
  height: 2px;
  border-radius: 1px;
  background: #000;
}

#router_view {
  position: absolute;
  height: 40px;
  width: 40px;
  background: #00b7ff;
  right: 20px;
  top: 0;
  bottom: 0;
  margin: auto;
}

.b_t {
  position: absolute;
  top: 0;
  bottom: 20px;
  margin: auto;
}

.b_c {
  position: absolute;
  top: 0;
  bottom: 0;
  margin: auto;
}

.b_b {
  position: absolute;
  top: 20px;
  bottom: 0;
  margin: auto;
}

#mobile_router {
  min-width: none;
  position: absolute;
  z-index: -1;
  left: 0;
  right: 0;
  width: 100%;
  height: 200px;
  background: #00ff99;
  margin: 0;
}

.y {
  position: static;
  text-align: center;
  margin: auto;
  left: 20px;
}
</style>

<script>
export default {
  data() {
    return {
      isActive01: false,
      windowWidth: window.innerWidth
    }
  },
   mounted () {
      window.onload = ()=>{
        this.windowload;
      }
      window.addEventListener('resize', this.resizeWindow)
   },
   methods: {
      resizeWindow () {
         this.windowWidth = window.innerWidth
      },
      windowload () {
        this.windowWidth = window.innerWidth
      }
   }
}
</script>