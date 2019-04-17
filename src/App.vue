<template >
  <v-app style="
    background: black;
  ">
    <v-navigation-drawer
      v-model="drawerRight"
      fixed
      right
      clipped
      app
    >
     
    </v-navigation-drawer>
    <v-toolbar
      black
      fixed
      app
      clipped-right
    >
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Crazy Animes</v-toolbar-title>
    <v-spacer>

      



    </v-spacer>

    <v-btn icon>
      <v-icon>search</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>apps</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>refresh</v-icon>
    </v-btn>  

    <v-btn icon>
      <v-icon>more_vert</v-icon>
    </v-btn>

    </v-toolbar>

    
    <v-navigation-drawer
      v-model="drawer"
      fixed
      app
    >
    </v-navigation-drawer>
      
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      drawerRight: null,
      right: false,
      left: false
    }),
    props: {
      source: String
    }
  }
</script>


