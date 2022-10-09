<template>
  <div id="drink-button-container">
    <DrinkButton v-for="(drink, index) in drinks" :key='index'
      :name='drink.name'
      :price='drink.price'
      :id='drink.name'
      @addDrink="addDrink">
    </DrinkButton>
  </div>

  <div id="bill-display-container">
    <BillDisplay
      :itemsCount='itemsCount'
      :totalPrice='totalPrice'>
    </BillDisplay>
  </div>
</template>

<script>
import DrinkButton from './components/DrinkButton.vue'
import BillDisplay from './components/BillDisplay.vue'

export default {
  name: 'App',
  components: {
    DrinkButton,
    BillDisplay
},
  data() {
    return {
      drinks: [{name: 'coffee', price: 480},
               {name: 'tea', price: 280},
               {name: 'milk', price: 180},
               {name: 'coke', price: 190},
               {name: 'beer', price: 580}],
      itemsCount: 0,
      totalPrice: 0
    }
  },

  methods: {
    addDrink(price) {
      this.itemsCount += 1
      this.totalPrice += price
    }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#drink-button-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

#bill-display-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px 0 0 0;
}
</style>
