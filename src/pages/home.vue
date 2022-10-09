<template>
  <div class="home">
    <div class="header">
        <img src="https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqazE3Q2MxUDQtVmRsMmRxaDhiNVVOd1JjSUFnUXxBQ3Jtc0ttSC1MRXlFdHlWaVJYRzd3MXZtdVZQc3FIZmh1c3pvS0pUOVFsZDR4QUd4VzV6SUdDWm83cEhidGR5RHk2SVVKcm1NbzhmUVl1VVhSTlM3THRldFJ3cWJhZU1uTlJVLTVXWVUwb2F2V3ZwNTNyZWlCWQ&q=https%3A%2F%2Fd3i4yxtzktqr9n.cloudfront.net%2Fweb-eats-v2%2Fee037401cb5d31b23cf780808ee4ec1f.svg&v=6VdnbFi0tdQ" alt="">
        <input type="text" placeholder="de quoi avez vous besoin?">
    </div>
    <div class="bannier">

    </div>
   <restaurantRow  v-for="(Data, i) in Data_restaurant" :key="i" :three_restaurant="Data"/> 
  </div>
</template>

<script>
//Import 
import BDD from '../BDD.js'
import { onMounted , ref } from 'vue'
//components
import restaurantRow from '../components/restaurantRow.vue'
export default {
    name: 'homePage',
    components: {
        restaurantRow, 
    },
    setup() {
        class Restaurant {
            constructor ( name, note , image , drive_time) {
                this.name = name;
                this.note = note;
                this.image =  image;
                this.drive_time = drive_time;
            }
            
        }
        let Data_restaurant = ref ([]);

        const makeDataRestaurant = () => {
            let three_restaurant = []

            for (const restaurant of BDD) {
                const new_restaurant = new Restaurant(restaurant.name, restaurant.note, restaurant.image, restaurant.drive_time)
            if (three_restaurant.length === 2) {
                three_restaurant.push(new_restaurant);
                Data_restaurant.value.push(three_restaurant);
                three_restaurant = [];
            
            }
            else {
                three_restaurant.push(new_restaurant);
            }   
        }        
        }

        onMounted(makeDataRestaurant);
        //return 
        return {
            Data_restaurant,
        }
    },
}
</script>

<style lang="scss">
.home {
    .header{
        height: 120px;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        img{
            width: 200px;
        }
        input {
            background: #f6f6f6;
            border: none;
            height: 60px;
            width: 400px;
            outline: none;
            padding: 0px 20px;
        }
    }
    .bannier {
        height: 200px;
        width: 100px;
        background-image: url("https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbGJLQzZZcnE0T0xEczNsXzlGbmJGUy1RRFpkUXxBQ3Jtc0tuVHdZTUpfVFJtclVGNDM2blNJWlZxa0Nld1U0SGdzU1lneGpsZ2d2dEdmM0tHWDRpYS1ZOXFzY04zdmd5Z3UzVVdXQVVLSm0tQXJyWUNxVThVSExfNUhVcm15MDE3cW95YmNFUzFHRHVpWHdld2R1TQ&q=https%3A%2F%2Fwww.ubereats.com%2Frestaurant%2F_static%2F7b308f7cbbf8e335ceda0447a8bd7c63.png&v=6VdnbFi0tdQ");
        background-size: cover;
        padding-lef: 20px;
    }
}
</style>