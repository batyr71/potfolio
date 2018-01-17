<template>
  <v-content>
    <v-container>
      <h2 class ="display-1 mb-3">Some of my works</h2>
      <v-layout row wrap>
        <v-flex sm5 md4 v-for="item in items" :key="item.title" class="mx-auto mb-3 pa-2">
          <v-card>
            <v-card-title primary-title>
              <div >
                <h3 class="headline mb-1">{{ item.title }}</h3>
                <div>Located two hours south of Sydney in the Southern Highlands of New South Wales, ...</div>
              </div>
            </v-card-title>
            <v-card-media >
              <img :src="item.pic" :alt="item.title" class="px-3" height="100%">
            </v-card-media>
            <v-card-actions>
              <v-btn flat color="orange"  @click="goTo(item.git)">Go to Github</v-btn>
              <v-btn flat color="orange"  @click="goTo(item.site)">Go to website</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </v-content>
</template>

<script>
  export default {
    data: () => ({
      items: [
        { title: 'magazine', 
          git:"https://github.com/batyr71/magazine" , 
          site: "https://batyr71.github.io/magazine/", 
          pic: "/static/magazine.png" },
        { title: 'hommard', 
          git:"https://github.com/batyr71/hommard" , 
          site: "https://batyr71.github.io/hommard/", 
          pic: "/static/hommard.png" },
        { title: 'commode', 
          git:"https://github.com/batyr71/commode" , 
          site: "https://batyr71.github.io/commode/", 
          pic: "/static/commode.png" },
        { title: 'parrots-test', 
          git:"https://github.com/batyr71/parrots-test" , 
          site: "https://batyr71.github.io/parrots-test/", 
          pic: "/static/parrots-test.png" },
        { title: 'garagetest', 
          git:"https://github.com/batyr71/garagetest" , 
          site: "https://batyr71.github.io/garagetest/", 
          pic: "/static/garagetest.png" },
        { title: 'vuetable', 
          git:"https://github.com/batyr71/vuetable" , 
          site: "https://batyr71.github.io/vuetable/", 
          pic: "/static/vuetable.png"},
      ]
    }),
    methods: {
      goTo(link) {
        window.open(link, '_blank');
      },
    }
  }
</script>