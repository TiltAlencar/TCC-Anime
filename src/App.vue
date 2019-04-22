<template >
  <v-app style="
    background: black;
    color: white;
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

      
    <!-- itens do menu -->  


    
    </v-spacer>
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
    <!-- fim menu -->

    
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