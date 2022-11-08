<template>
      <v-container class="grey lighten-5"  >
    <v-row>
    <v-col cols="12" v-for="tile in tiles" :key="tile.title">
      <v-card
    class="mx-auto card images"
    max-width="344"
    color="black"
    :to="tile.to"
    :style="{backgroundImage: `url(${tile.img})`}"
  >      <v-btn value="recent" color="orange">
      <v-icon>{{tile.icon}}</v-icon>
    </v-btn>
    <v-card-text>

      <p class="text-h4 text-center">
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
        title: 'CRM',
        icon: ' mdi-account',
        text: 'Customer Relational Manager',
        img: "https://i.postimg.cc/C5LrDVyz/CRM.jpg",
        category: [
          'admin'
        ],
        to: '/crm'
      },
      {
        title: 'Quotes',
        icon: 'mdi-format-quote-close ',
        text: 'Quote Generations System',
        img: "https://i.postimg.cc/bwSFWbhN/Quotations.jpg",
        category: [
          "admin"
        ],
        to: '/quotes'
      },
      {
        title: 'WO',
        icon: 'mdi-briefcase',
        text: 'Works Orders',
        img: "https://i.postimg.cc/htfPwKM1/WO.jpg",
        category: [
          "admin"
        ],
        to: '/wo'gfit
      },
      {
        title: 'DAR',
        icon: 'mdi-chart-box',
        text: '',
        img: "",
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
.images{
  background-size: cover;
  background-repeat: no-repeat;
  background-position:center ;
}
.v-application .text-h4 {
    font-size: 2.125rem !important;
    font-weight: 400;
    color: white;
    line-height: 2.5rem;
    letter-spacing: 0.0073529412em !important;
    font-family: "Roboto", sans-serif !important;
}
</style>
