<template>
  <v-app dark> <!--body-->
    <div class="login">
      <v-form
        ref="form"
        v-model="valid"
        lazy-validation
      >
        
        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="E-mail"
          required
        ></v-text-field>

        <v-text-field
          v-model="Senha"
          :counter="10"
          :rules="nameRules"
          label="Senha"
          required
          type="password"
        
        ></v-text-field>

        <v-checkbox
          v-model="checkbox"
          :rules="[v => !!v || 'You must agree to continue!']"
          label="Do you agree?"
          required
        ></v-checkbox>

        <v-btn
          :disabled="!valid"
          color="success"
          @click="validate"
        >
          Validate
        </v-btn>

        <v-btn
          color="error"
          @click="reset"
        >
          Reset Form
        </v-btn>

        <v-btn
          color="warning"
          @click="resetValidation"
        >
          Reset Validation
        </v-btn>
      </v-form>
    </div>
  </v-app>
</template>

<style>
  .login{

    margin-left: 75pt;
    margin-right: 75px;

  }

</style>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      //
    }
  }
}
</script>
