<template>
  <li :class="msg">
    {{ name }}
  </li>
</template>

<script>
export default {
  data() {
    return {
      msg : 'active'
    }
  },
  props : {
    name: {
      type:String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
  li {
    color: red;
  }
  .active {
    font-size: 10px;
  }
</style>