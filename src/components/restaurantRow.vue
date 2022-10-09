<template>
  <div class="restaurant--row">
    <h2 class="title">
        nos restaurant 
        
    </h2>
    <div class="wrapper--card">
      <restaurant-card v-for="(card, index) in three_restaurant" :info_Restaurant="card" :key="index"/>
    </div>
  </div>
</template>

<script>
import RestaurantCard from './restaurantCard.vue';

export default {
    name: "restaurantRow",
    components:{
      RestaurantCard,
    },
    props:{
      three_restaurant: Array
    }
}
</script>

<style lang="scss">
.restaurant--row{
  .wrapper--card{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}

</style>