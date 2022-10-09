<template>
  <div class="restaurant--card">
    <div :style="changeBackground" class="restaurant--image">
      <!-- -->
    </div>
    <div class="restaurant--informations">
        <div class="top">
            <p class="name">
                {{ info_Restaurant.name}}
            </p>
            <p class="note">
               <span>
                {{info_Restaurant.note}}
               </span> 
            </p>
        </div>
        <p class="time"> 
            {{ info_Restaurant.drive_time }} 
        </p>
    </div>
    
  </div>
</template>

<script>
//import
import{ computed } from 'vue'
export default {
    name:"restaurantCard",
    props : {
        info_Restaurant: Object
    },
    setup(props) {
        const changeBackground= computed(() => {
            return{
                backgroundImage:`url(${props.info_Restaurant.image})`
            }
        })
        
        
        //return
        return{
            changeBackground
        }
    }
}
</script>

<style lang="scss">
.restaurant--card{
    width: 32%;
    height: 30vh;
    
    p{
        margin: 0;
    }
    .restaurant--image{
        background-image: url("https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa0lOTlBqOHZRM2hNS1BMb2tHaTQ1UE1WYjRrUXxBQ3Jtc0tsb1E1REdLUnk4TGdFTGJ5aXJCeU9XOXJ0OWlMZ2pZQXZwaGNnS3hoM0tGbXlrWTdEUFlDaEVSdnhYeWhoNWdESGdQcHhoNE9xOGVmT2RSUFBLSU5vMmJuUmhSNnM1aG01VnJSdXREUlZCN19ocXBoYw&q=https%3A%2F%2Fcn-geo1.uber.com%2Fimage-proc%2Fresize%2Feats%2Fformat%3Dwebp%2Fwidth%3D550%2Fheight%3D440%2Fquality%3D70%2Fsrcb64%3DaHR0cHM6Ly9kMXJhbHNvZ25qbmczNy5jbG91ZGZyb250Lm5ldC8zNzg4MDJiMC1jNTI4LTQ4MjktYjBiNS0wY2M2NDBkZjYzY2QuanBlZw%3D%3D&v=4eGlmXWCpSs");
        height: 70%;
        background-size: conver;
        background-position: center;

        img{
            height: 100%;
            width: 100%;
            object-fit: cover;
        }
    }
    .restaurant--informations{
        .top{
            margin: 10px 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            .note{
                background-image: #eeee;
                height: 30px;
                width: 30px;
                display: flex;
                justify-content: center;
                align-items: center;
            }
        }
        .time{
            background-image: #eeee;
            font-size: 0.9rem;
            margin-left: 10px;
        }
    }
}


</style>