<template>
  <div id="app">
    this is app
    <!-- <button @click="passMsg">传你</button>
    <m-parent :msga="a" :msgb="b" :msgc="c"></m-parent> -->
    <!-- <router-link to="/home">home</router-link>
    <button @click="toHome">home</button> -->
    <router-view></router-view>
  </div>
</template>

<style>

</style>

<script>
import MParent from './views/Parent'
import bus from './util/bus'
export default {
  components: {
    MParent,
  },
  data() {
    return {
      a: 'msga',
      b: 'msgb',
      c: 'msgc',
    }
  },
  methods: {
    passMsg() {
      bus.$emit('msg','i am from app')
    },
    toHome() {
      // this.$router.push({path: '/home',query: {name: 'Jack'}}) //固定搭配
      this.$router.push({name: 'home',params: {id: 5}}) 
    }
  },
}
</script>