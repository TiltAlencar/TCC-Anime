<template>
  <v-app id="inspire" style="
  background: rgba(165,0,173,1);
background: -moz-linear-gradient(top, rgba(165,0,173,1) 0%, rgba(153,0,133,1) 44%, rgba(76,0,92,1) 100%);
background: -webkit-gradient(left top, left bottom, color-stop(0%, rgba(165,0,173,1)), color-stop(44%, rgba(153,0,133,1)), color-stop(100%, rgba(76,0,92,1)));
background: -webkit-linear-gradient(top, rgba(165,0,173,1) 0%, rgba(153,0,133,1) 44%, rgba(76,0,92,1) 100%);
background: -o-linear-gradient(top, rgba(165,0,173,1) 0%, rgba(153,0,133,1) 44%, rgba(76,0,92,1) 100%);
background: -ms-linear-gradient(top, rgba(165,0,173,1) 0%, rgba(153,0,133,1) 44%, rgba(76,0,92,1) 100%);
background: linear-gradient(to bottom, rgba(165,0,173,1) 0%, rgba(153,0,133,1) 44%, rgba(76,0,92,1) 100%);
filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#a500ad', endColorstr='#4c005c', GradientType=0 );">
    <v-navigation-drawer
      v-model="drawer"
      clipped
      fixed
      app
    >
      <v-list dense>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon>dashboard</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Dashboard</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon>settings</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Settings</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
       <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon>gavel

            </v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Animes</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
      <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon>widgets</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Mangás</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
      <v-list-tile @click="algo">
          <v-list-tile-action>
            <v-icon>event</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Alguma coisa</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app fixed clipped-left>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Crazy Animes</v-toolbar-title>
       
    <v-spacer></v-spacer>

        
      <v-btn flat>Animes</v-btn>
      <v-btn flat>Mangás</v-btn>

<!-- botão login -->
    <template>
      <div class="text-xs-center">
        <v-dialog
          v-model="dialog"
          width="500"
        >
          <template v-slot:activator="{ on }">
            <v-btn
            
              dark
              v-on="on"
            >
              Ainda não tem uma conta?
            </v-btn>
          </template>

          <template>
            <v-layout>
              <v-flex xs12 sm6 offset-sm3>
                <v-card>
                  <v-img
                    class="white--text"
                    height="200px"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-container fill-height fluid>
                      <v-layout fill-height>
                        <v-flex xs12 align-end flexbox>
                          <span class="headline">Top 10 Australian beaches</span>
                        </v-flex>
                      </v-layout>
                    </v-container>
                  </v-img>
                  <v-card-title>
                    <div>
                      <span class="grey--text">Number 10</span><br>
                      <span>Whitehaven Beach</span><br>
                      <span>Whitsunday Island, Whitsunday Islands</span>
                    </div>
                  </v-card-title>
                  <v-card-actions>
                    <v-btn flat color="orange">Share</v-btn>
                    <v-btn flat color="orange">Explore</v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
            </v-layout>
          </template>
        </v-dialog>
      </div>
    </template>

<!-- fim botão login -->
      
      </v-toolbar>

<!-- Carrossel -->
  <div id="carrossel">
  <template>
    <v-carousel hide-controls>
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
      ></v-carousel-item>
    </v-carousel>
  </template>
  </div>
<!-- Fim carrossel -->
    
  </v-app>
</template>


<style>

#carrossel{
  width:95%;
  margin-top:8%;
  margin-left:2.5%; 
}

</style>


<script>
  export default {
    data: () => ({
      drawer: null
    }),
    props: {
      source: String
    }
  }
</script>

<!-- Login -->
<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4'
      ],
      checkbox: false
    }),

    methods: {
      validate () {
        if (this.$refs.form.validate()) {
          this.snackbar = true
        }
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      }
    }
  }
</script>

<!-- Fim Login -->

<!-- Carrossel -->
<script>
  export default {
    data () {
      return {
        items: [
          {
            src: require('@/assets/naruto.jpg')
          },
          {
            src: require('@/assets/no-game-no-life.jpg')
          },
          {
            src: require('@/assets/death-note.jpg')
          },
          {
            src: require('@/assets/dragon-ball.jpg')
          }
        ]
      }
    }
  }
</script>

<!-- Fim Carrossel -->


