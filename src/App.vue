<template>
  <v-app id="inspire">
    <v-navigation-drawer  v-model="drawer" app color="black">
      <v-list-item class="backgrd" color="white">
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Menu
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title class="drw_list">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <template v-slot:append>
        <div class="pa-2">
          <v-btn block @click="logOut" to="/">
            Logout
          </v-btn>
        </div>
      </template>
    </v-navigation-drawer>

    <v-app-bar color="black" app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title><img class="company_logo" src="https://i.postimg.cc/HkgChgDH/Company-Logo.jpg" alt="">
      </v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view />

      <BottomNav/>

    </v-main>

  </v-app>
</template>


<script>
import BottomNav from '@/components/BottomNav.vue'
export default {
  name: 'App',
  data() {
    return {
      items: [
        { title: 'User Profile', icon: 'mdi-account-circle-outline', to: '/userprofile' },
        { title: 'Settings', icon: 'mdi-cog-outline', to: '/settings' }
      ],
      drawer: null,
    }
  },
  components: {
    BottomNav,
  },
  computed: {
    user() {
      return this.$store.state.user
    }
  },
  methods: {
    logOut() {
      return (this.$store.state.user = null,
        localStorage.removeItem('vuex')
      )
    }
  }
}
</script>

<style>
.filters{
  margin-bottom: 5%;
}
.table{
  background-color: white;
  border-radius: 10px;

}

.table__heading {
    border-bottom: solid 2px #FF8418 !important;
    border-top: none
}
.v-main__wrap{
  background:url("https://i.postimg.cc/0NKwRsL5/Wallpaper.jpg") no-repeat center center/cover;
}
.company_logo {
  width: 6.5%;
}

.v-app-bar {
  z-index: 1000 !important;
}


.backgrd {
  background: linear-gradient(to top,black, #FF8418);
  border: none !important;
  color: white;
}

.text-h6 {
  color: white;
}

.account {
  color: #FF8418 !important;
}

.mdi-account-circle::before {
  content: "\F0009";
  color: #FF8418 !important;
}

.pa-3 {
  color: #fb8c00 !important;
}

.mdi-microphone::before {
  content: "\F036C";
  color: #FF8418 !important;
}

::before {
  text-decoration: inherit;
  vertical-align: inherit;
  color: #FF8418 !important;
}

.drw_list {
  color: white;
}

.mdi-delete::before {
  content: "\F01B4";
  color: white !important;
}





.mdi-close::before {
  content: "\F0156";
  color: white !important;
}

.mdi-account-group::before {
    content: "\F0849";
    color: white !important;
}

.mdi-wall::before {
    content: "\F07FE";
    color: white !important;
}

.mdi-home-group::before {
    content: "\F0DD4";
    color: white !important;
}

.v-input--selection-controls__ripple {
  color: #FF8418;
}

.v-input--selection-controls__ripple:before {
  border-radius: inherit;
  bottom: 0;
  content: "";
  position: absolute;
  opacity: 0.2;
  left: 0;
  right: 0;
  top: 0;
  transform-origin: center center;
  transform: scale(0.2);
  transition: inherit;
  color: #FF8418 !important;
}

.v-application .primary--text {
  color: #FF8418 !important;
  caret-color: #1976d2 !important;
}

.mdi-domain::before {
  content: "\F01D7";
  color: white !important;
}

.mdi-message-text::before {
  content: "\F0369";
  color: white !important;
}

.mdi-account::before {
  content: "\F0004";
  color: white !important;
}

.mdi-account-tie::before {
  content: "\F0CE3";
  color: white !important;
}

.mdi-briefcase::before {
  content: "\F00D6";
  color: white !important;
}

.mdi-format-quote-close::before {
  content: "\F027E";
  color: white !important;
}

.mdi-cart-arrow-down::before {
  content: "\F0D66";
  color: white !important;
}

.mdi-chart-box::before {
  content: "\F154D";
  color: white !important;
}

.mdi-factory::before {
  content: "\F020F";
  color: white !important;
}

.mdi-store-edit-outline::before {
  content: "\F18CA";
  color: white !important;
}

.mdi-cash-multiple::before {
  content: "\F0116";
  color: white !important;
}

.mdi-home::before {
  content: "\F02DC";
  color: white !important;
}

.primary {
  color: #FF8418 !important;
}

@media (max-width: 425px) {
  .company_logo {
    width: 30%;
  }
}


@media (width: 425px) {
  .company_logo {
    width: 25%;
  }
}

.v-application a {
    text-decoration: none !important;
}
</style>