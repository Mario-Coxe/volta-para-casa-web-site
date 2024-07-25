<template>
  <v-row class="d-flex justify-center align-center fill-height" style="min-height: 100vh;">
    <v-col cols="12" md="6">
      <v-card class="py-6 px-4">
        <v-card-title class="d-flex justify-center">
          <span class="text-h4 font-weight-bold">Login</span>
        </v-card-title>
        <v-card-text>
          <v-form ref="form">
            <v-text-field v-model="phone" label="Número de Telefone" outlined required prepend-icon="mdi-phone"
              :rules="[rules.required, rules.phone]"></v-text-field>
            <v-text-field v-model="password" label="Password" outlined required prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'" :type="showPassword ? 'text' : 'password'"
              @click:append="showPassword = !showPassword" :rules="[rules.required]"></v-text-field>
            <v-row class="mt-4">
              <v-col class="text-right">
                <v-btn color="primary" @click="submit">
                  Login
                </v-btn>
              </v-col>
            </v-row>
            <v-row class="mt-2">
              <v-col class="text-center">
                <v-btn text @click="redirectToRegister">
                  Não tem uma conta? Registre-se aqui.
                </v-btn>
              </v-col>
            </v-row>
          </v-form>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      phone: '',
      password: '',
      showPassword: false,
      rules: {
        required: value => !!value || 'Campo obrigatório.',
        phone: value => /^(?:\+244|244)?9\d{8}$/.test(value) || 'Número de telefone deve ser válido.',
      },
    };
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        // Implement login logic here
        alert('Login bem-sucedido!');
      }
    },
    redirectToRegister() {
      // Implement the logic to redirect to the registration page
      this.$router.push('/register');
    },
  },
};
</script>

<style scoped>
.v-card-title {
  font-size: 24px;
  font-weight: bold;
}

.v-card-text {
  padding-top: 0;
}
</style>
