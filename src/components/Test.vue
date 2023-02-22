<template>
  <h2 @click="increase">
    {{ count }}
  </h2>
  <div v-if="count > 4">
    4보다 큽니다.
  </div>
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruit"
      :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>
<script>
import Fruit from "~/components/Fruit";

export default {
  components: {
    Fruit : Fruit
  },
  data() {
    return{
      count : 0,
      fruits : ['Apple', 'Banana', 'Cherry']
    }
  },
  methods: {
    increase() {
      this.count += 1
    }
  }
}
</script>
<style lang="scss">


</style>