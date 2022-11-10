<template>
      <v-container class="grey lighten-5"  >
    <v-row class="boxes">
    <v-col class="back_admin" cols="12" sm="3" v-for="tile in tiles" :key="tile.title">
      <v-card
    class="mx-auto card images"
    max-width="344"
    :to="tile.to"
    :style="{backgroundImage: `url(${tile.img})`}"
  >      <v-btn value="recent" class="btn_icons" >
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
        title: 'CRM',
        icon: ' mdi-account',
        text: 'Customer Relational Manager',
        img: "https://i.postimg.cc/htFwpWQn/CRM.jpg",
        category: [
          'admin'
        ],
        to: '/crm'
      },
      {
        title: 'Quotes',
        icon: 'mdi-format-quote-close ',
        text: 'Quote Generations System',
        img: "https://i.postimg.cc/T3LWCn6B/Quotations.jpg",
        category: [
          "admin"
        ],
        to: '/quotes'
      },
      {
        title: 'WO',
        icon: 'mdi-briefcase',
        text: 'Works Orders',
        img: "https://i.postimg.cc/gkyqFfBm/WO.jpg",
        category: [
          "admin"
        ],
        to: '/wo'
      },
      {
        title: 'DAR',
        icon: 'mdi-chart-box',
        text: '',
        img: "https://i.postimg.cc/htJdYKbm/DAR.jpg",
        category: [
          "admin"
        ],
        to: '/reports'
      },
 

    ],
    })
}
</script>

<style scoped>
.btn_icons{
  background-color: gray !important;
}




.boxes{
  height: 100%;
 
}
.v-main__wrap {
  overflow-y:hidden !important;
}
.back_admin:nth-child(even) {
  background-color: black
}
.back_admin:nth-child(odd){
  background-color: #FF8418;
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
