<template>
  <div>
    <el-button
      type="primary"
      icon="el-icon-refresh"
      @click="random"
    > چارەسەرکردنی هاوکێشەی هەڕەمەکی </el-button>
   </div>
</template>

<script>
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
