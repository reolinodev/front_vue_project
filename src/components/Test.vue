<template>
  <h2 @click="increase">
    {{ count }}
  </h2>
  <div v-if="count > 4">
    4보다 큽니다.
  </div>
  <section v-if="hasFruit">
    <h1>Fruit</h1>
    <ul>
      <Fruit
        v-for="fruit in fruits"
        :key="fruit"
        :name="fruit">
        {{ fruit }}
      </Fruit>
    </ul>
  </section>
  <section>
    <h1>reverse Fruit</h1>
    <ul>
      <Fruit
        v-for="fruit in reverseFruits"
        :key="fruit"
        :name="fruit">
        {{ fruit }}
      </Fruit>
    </ul>
  </section>
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
  },
  computed: {
    hasFruit() {
      return this.fruits.length > 0
    },
    reverseFruits() {
      return this.fruits.map(fruit => {
       return fruit.split('').reverse().join('')
      })
    }
  }
}
</script>
<style lang="scss">


</style>