<template>
  <v-app dark>
    <v-navigation-drawer temporary clipped fixed v-model="drawer" app right >
      <v-list v-for="item in menuItems" :key="item" >
        <v-list-tile router :to="item.route">
          <v-list-tile-action >
            <v-icon>{{item.icon}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>{{item.title}}</v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer> 
    <v-toolbar app fixed clipped-right>
      <v-toolbar-title><router-link router to="/" tag='span' style="cursor:pointer" v-text="title"></router-link></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down"  v-for="item in menuItems" :key="item">
         <v-btn flat router :to="item.route"><v-icon left>{{item.icon}}</v-icon>{{item.title}}</v-btn>
      </v-toolbar-items>
      <v-toolbar-side-icon class="hidden-md-and-up" @click.stop="drawer = !drawer" ></v-toolbar-side-icon>
    </v-toolbar>
    <v-container>

    <main >
      <router-view ></router-view>
    </main>
    </v-container>
    <v-footer fixed>&copy Made with<span class="green--text">Vue.js</span></v-footer>
  </v-app>
</template>

<script>
  export default {
    data : () => ({
        title: "{{ batyr.info }}",
        drawer: false,
        menuItems: [
          { icon: 'account_circle', title: 'About', route: "/about"},
          { icon: 'apps', title: 'Portfolio', route: '/portfolio'},
          { icon: 'build', title: 'Skills', route: "/skills"},
          { icon: 'email', title: 'Contact', route: "/contact"},
          ]
      }),
  }
</script>
