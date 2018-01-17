<template>
   <v-content>
    <v-container >
      <h4 class="display-1">My skills and using tools</h4>
      <p class="display-1 mt-3" >
        <span v-for="item in items" :key="item.title">
          <code >{{item.title}}</code>&nbsp</span>
      </p>
    </v-container>
  </v-content>
</template>

<script>
  export default {
    data: () => ({
      items: [
        { title: 'HTML5' },
        { title: 'CSS3' },
        { title: 'Javascript' },
        { title: 'PHP7' },
        { title: 'Laravel'},
        { title: 'Vue.js'},
        { title: 'Vuetify'},
        { title: 'axios.js'},

      ]
    })
  }
</script>