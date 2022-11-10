<template>
    <div class="container">
  <router-link to="/reports">
  <v-row class="shape image_1" >
      <v-container>
          <h1 class="backs dar">SAR</h1>
      </v-container>
  </v-row>
  </router-link>
  <router-link to="/quotes">
  <v-row class="shape image_2">
      <v-container>
          <h1 class="backs quote">Quotations</h1>
      </v-container>
  </v-row>
  </router-link>
    </div>
  </template>
  
  <script>
  export default {
  
  }
  </script>
  
  <style scoped>
  .container{
  height:400px;
  }
  .image_1{
  background: linear-gradient(rgba(255, 132, 24, 0.802),rgba(16, 15, 15, 0.163)) ,url("https://i.postimg.cc/5Ng0yfCt/SAR.webp");
     background-size: cover;
    background-repeat: no-repeat;
    background-position:top;
  }
  
  .image_2{
  background: linear-gradient(to top,rgba(255, 132, 24, 0.802),rgba(16, 15, 15, 0.163)) ,url("https://i.postimg.cc/T3LWCn6B/Quotations.jpg");
     background-size: cover;
    background-repeat: no-repeat;
    background-position:center;
  }
  
  .backs{
      background-color: rgba(0, 0, 0, 0.502);
      border-radius: 10px;
      padding-left:10px;
      padding-right:10px;
      color:white;
  }
  
  .dar{
      width:108px;
  }
  .quote{
  width:240px;
  }
  @media (min-width: 1264px){
.container {
    max-width: 1437px;
}
}
  </style>