<template>
  <div>
    <button @click="toggleDiv(0)">显示/隐藏Div1</button>
    <div v-show="divVisibilities[0]">Div 1</div>
 
    <button @click="toggleDiv(1)">显示/隐藏Div2</button>
    <div v-show="divVisibilities[1]">Div 2</div>
 
    <button @click="toggleDiv(2)">显示/隐藏Div3</button>
    <div v-show="divVisibilities[2]">Div 3</div>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      // 初始化三个div的显示状态数组
      divVisibilities: [true, true, true]
    };
  },
  methods: {
    toggleDiv(index) {
      // 切换对应div的显示状态
      this.divVisibilities[index] = !this.divVisibilities[index];
    }
  }
};
</script>