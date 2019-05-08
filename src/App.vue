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
      <v-list-tile @click="">
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

          <v-card>
            <v-card-title
              class="headline grey lighten-2"
              primary-title
            >
              REGISTRAR CONTA!
            </v-card-title>

            <v-card-text>
              <template>
              <v-card
                class="mx-auto"
                max-width="500"
              >
                <v-card-title class="title font-weight-regular justify-space-between">
                  <span>{{ currentTitle }}</span>
                  <v-avatar
                    color="primary lighten-2"
                    class="subheading white--text"
                    size="24"
                    v-text="step"
                  ></v-avatar>
                </v-card-title>

                <v-window v-model="step">
                  <v-window-item :value="1">
                    <v-card-text>
                      <v-text-field
                        label="Email"

                      ></v-text-field>
                      <span class="caption grey--text text--darken-1">
                        Insira seu email acima!!
                      </span>
                    </v-card-text>
                  </v-window-item>

                  <v-window-item :value="2">
                    <v-card-text>
                      <v-text-field
                        label="Senha"
                        type="password"
                      ></v-text-field>
                      <v-text-field
                        label="Confirme sua senha"
                        type="password"
                      ></v-text-field>
                      <span class="caption grey--text text--darken-1">
                        Insira sua senha acima!!
                      </span>
                    </v-card-text>
                  </v-window-item>

                  <v-window-item :value="3">
                    <div class="pa-3 text-xs-center">
                      <v-img
                        class="mb-3"
                        contain
                        height="128"
                        src="IMAGEM AQUI"
                      ></v-img>
                      <h3 class="title font-weight-light mb-2">Bem Vindo ao Crazy Animes!</h3>
                      <span class="caption grey--text">Obrigado por criar sua conta! sua alma agora é nossa ;)</span>
                    </div>
                  </v-window-item>
                </v-window>

                <v-divider></v-divider>

                <v-card-actions>
                  <v-btn
                    :disabled="step === 1"
                    flat
                    @click="step--"
                  >
                    Voltar
                  </v-btn>
                  <v-spacer></v-spacer>
                  <v-btn
                    :disabled="step === 3"
                    color="primary"
                    depressed
                    @click="step++"
                  >
                    Próximo
                  </v-btn>
                </v-card-actions>
              </v-card>
            </template>
            </v-card-text>
            <v-divider></v-divider>
          </v-card>
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
  display:flex;
  justify-content:10px;
  height:16%;
  margin-top:8%;
  margin-left:2.5%;
  position:absolute;
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
    data () {
      return {
        dialog: false
      }
    }
  }
</script>

<script>
  export default {
    data: () => ({
      step: 1
    }),

    computed: {
      currentTitle () {
        switch (this.step) {
          case 1: return 'Criar conta'
          case 2: return 'Crie sua senha'
          default: return 'Conta registrada'
        }
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
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          }
        ]
      }
    }
  }
</script>

<!-- Fim Carrossel -->


