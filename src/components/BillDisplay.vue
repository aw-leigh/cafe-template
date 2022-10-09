<template>
  <v-card max-width="400" class="justify-center">
    <v-card-title>Your Bill</v-card-title>
    <v-card-text>Items ordered: </v-card-text><v-card-text id="count"> {{itemsCount}}</v-card-text>
    <v-card-text>Total price: </v-card-text><v-card-text id="price"> {{totalPrice}}</v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    itemsCount: Number,
    totalPrice: Number
  },
}
</script>

<style scoped>
#price, #count {
  padding: 0 0 0 0
}
</style>
