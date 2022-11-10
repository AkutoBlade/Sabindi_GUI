<template>
    <v-container class="grey lighten-5"  >
  <v-row class="boxes">
  <v-col class="back_admin" cols="12" sm="3" v-for="tile in tiles" :key="tile.title">
    <v-card
  class="mx-auto card images"
  max-width="344"
  color="black"
  :to="tile.to"
  :style="{backgroundImage: `url(${tile.img})`}"
>      <v-btn value="recent" color="#FF8418">
    <v-icon>{{tile.icon}}</v-icon>
  </v-btn>
  <v-card-text>

    <p class="text-h4 titles text-center">
     {{tile.title}}
    </p>
  </v-card-text>
  <v-card-actions>
    <v-btn
      text
      color="orange accent-3"
    >

    </v-btn>
  </v-card-actions>
</v-card>
  </v-col>

  </v-row>  
  <!-- <BottomNav/> -->
</v-container>
</template>

<script>
export default {
data: () => ({ 
    drawer: null,
    tiles: [
    {
      title: 'Insurance',
      icon: 'mdi-account-group',
      text: 'Customer Relational Manager',
      img: "https://i.postimg.cc/JhyJRd1v/Insurance.jpg",
      category: [
        'admin'
      ],
      to: '/insurance'
    },
    {
      title: 'Residential',
      icon: 'mdi-wall',
      text: 'Quote Generations System',
      img: "https://i.postimg.cc/QVLpH2bH/Residential.webp",
      category: [
        "admin"
      ],
      to: '/residential'
    },
    {
      title: 'Corporate',
      icon: 'mdi-domain',
      text: 'Works Orders',
      img: "https://i.postimg.cc/bNznF95X/Corporate.webp",
      category: [
        "admin"
      ],
      to: '/corporate'
    },
    {
      title: 'Real Estate',
      icon: 'mdi-home-group',
      text: '',
      img: "https://i.postimg.cc/bNhv6Yss/Real-Estate.jpg",
      category: [
        "admin"
      ],
      to: '/property'
    },


  ],
  })
}
</script>

<style scoped>
.boxes{
  height: 100%;
 
}

.back_admin:nth-child(even) {
  background: black
}
.back_admin:nth-child(odd){
  background: gray;
}

.back_admin{
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;

}
.container{
  height: 100%;
} 
.titles{
-webkit-text-stroke: 0.5px rgba(255, 166, 0, 0.46);
background-color: rgba(0, 0, 0, 0.502);
border-radius: 10px;
}
.images{
background-size: cover;
background-repeat: no-repeat;
background-position:center ;
width: 100%;
}


.v-application .text-h4 {
  font-size: 2.125rem !important;
  font-weight: 400;
  color: white;
  line-height: 2.5rem;
  letter-spacing: 0.0073529412em !important;
  font-family: "Roboto", sans-serif !important;
}

.grey{
margin-bottom:20%;
}

@media (max-width: 32rem) {
  .boxes{
  height: 30%;
  margin-bottom: 20%;
}
}


</style>