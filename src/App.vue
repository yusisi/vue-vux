<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <group>
      <cell title="title" value="value"></cell>
    </group>
    <x-switch :title="title" v-model="show1"></x-switch>

    <actionsheet v-model="show1" :menus="menus1" @on-click-menu="click"></actionsheet> 
  </div>
</template>
<script>
import { Group, Cell,Alert ,Actionsheet,TransferDom,XSwitch,Toast   } from 'vux'
export default {
  name: 'App',
  components: {
    Group,
    Cell,
    XSwitch,
    Actionsheet ,
    Alert ,
    Toast
  },
   directives: {
    TransferDom
  },
  data() {
    return {
      title:"usage basic",
      show1: false,
      menus1: {
        menu1:"yes",
        menu2:"no"
      }
    }
  },
  methods: {
    
    click (key) {
      console.log(key)
    },
    
  }
};
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
