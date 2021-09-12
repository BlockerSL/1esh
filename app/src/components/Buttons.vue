<template>
  <div>
    <el-button
      type="primary"
      icon="el-icon-refresh"
      @click="random"
    > چارەسەرکردنی هاوکێشەی هەڕەمەکی </el-button>
    <el-button
      type="primary"
      icon="el-icon-view"
      @click="syntaxGuide = !syntaxGuide"
    >
      {{ syntaxGuide ? "Hide" : "" }} ڕێنوێنی سینتاکس
   </el-button>
 <SyntaxGuide :initialVisibility="syntaxGuide" @visibility="syntaxGuide = $event" />
  </div>
</template>

<script>
import SyntaxGuide from './SyntaxGuide.vue';
import { random as generateEquation } from '../library/chem-balancer';

export default {
  name: 'Buttons',
  components: { SyntaxGuide },
  props: {
    randomEquation: Function,
  },
  data() {
    return {
      syntaxGuide: false,
    };
  },
  methods: {
    random() {
      this.$emit('generateEquation', generateEquation());
    },
  },
};
</script>
<style>
button{
  border:1px solid white;
  border-radius: 15px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
  
}
</style>
