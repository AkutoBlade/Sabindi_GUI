<template>
    <v-bottom-navigation fixed color="#FF8418" v-model="value">
      <v-btn value="recent" v-for="item in items" :key="item.title" :to="item.to">
        <span>{{item.title}}</span>
  
        <v-icon>{{item.icon}}</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </template>

  <script>
     
    export default {
      name: 'BottomNav',
      data: () => ({
        value: 'recent',
    items: [
      { title: 'Business', icon: ' mdi-domain', to: "/sp" },
      { title: 'Admin', icon: ' mdi-account', to: "/admin" },
      { title: 'Clients', icon: ' mdi-account-group', to: "/clients" }
     
    ],
  }),
    }
</script>

<style scoped>
.v-bottom-navigation{
  background-color:black;
  height: 90px !important;
}
::before, ::after {
    text-decoration: inherit;
    color: white;
    vertical-align: inherit;
}

</style>