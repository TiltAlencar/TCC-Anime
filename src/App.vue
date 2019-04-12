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
          :counter="15"
          :rules="nameRules"
          label="Senha"
          required
          type="password"
        
        ></v-text-field>

        <v-checkbox
          v-model="checkbox"
          :rules="[v => !!v || 'Você não prometeu ainda!']"
          label="Prometo nunca te esquecer"
          required
        ></v-checkbox>

        <v-btn
          
          color="#7E57C2"
          @click="validate"
        >
          Validate
        </v-btn>

        <v-btn
          color="#18FFFF"
          @click="validate"
        >
          Validate
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
    }
  }
</script>