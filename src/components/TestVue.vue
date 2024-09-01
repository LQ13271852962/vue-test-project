<template>
  <div id="aapp">
    <div :class="divClass">Hello Vue!</div>
    <button @click="toggleClass">Toggle Class</button>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
  computed: {
    divClass() {
      return {
        active: this.isActive,
        inactive: !this.isActive
      };
    }
  },
  methods: {
    toggleClass() {
      this.isActive = !this.isActive;
    }
  }
};
</script>
 
<style>
.active {
  color: green;
}
.inactive {
  color: red;
}
</style>