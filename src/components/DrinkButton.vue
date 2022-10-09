<template>
  <v-container>
    <v-btn @click="incrementCounter" class="drink-button mx-1">
      {{name}} {{price}} yen
    </v-btn>
    <v-badge
      color="red"
      :content='count'>
    </v-badge>
    <div 
      :id="name + '-count'" class="hidden-count">
      {{count}}
    </div>
  </v-container>
</template>

<script>
export default {
  props: {
    name: String,
    price: Number
  },

  data() {
    return {
      count: 0
    }
  },

  methods: {
    incrementCounter() {
      this.count++
      this.$emit('addDrink', this.price)
    }
  }
}
</script>

<style scoped>
.hidden-count {
  display: none;
}
</style>
