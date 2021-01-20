<!--
 * @Descripttion: 
 * @version: 
 * @Author: zhangkun
 * @Date: 2021-01-20 18:55:34
 * @LastEditors: zhangkun
 * @LastEditTime: 2021-01-20 19:00:44
-->
<template>
  <div id="app">
    <butterfly-vue
      :canvasData="mockData"
      @onCreateEdge="logEvent"
      @onChangeEdges="logEvent"
      @onDeleteEdge="logEvent"
      @onOtherEvent="logEvent"
      @onLoaded="finishLoaded"
    />
  </div>
</template>

<script>
import ButterflyVue from 'butterfly-vue';
import 'butterfly-vue/index.css';
import mockData from "./mockData";

export default {
  name: 'App',
  components: {
    ButterflyVue
  },
  data(){
    return{
      mockData
    }
  },
  methods:{
    logEvent(e) {
      console.log(e);
    },
    finishLoaded(canvans) {
      console.log(canvans);
      console.log("finish");
    },
  }
}
</script>