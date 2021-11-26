<template>
<h1>login form</h1>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit.prevent= "loginForm"
      class="q-gutter-md"
    >
      <q-input
        filled
        label="mobile"
        v-model="mobile"
      />

      <q-input
        filled
        type="number"
        label="password"
        v-model="password"
      />

      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <!-- <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" /> -->
      </div>
    </q-form>

  </div>
</template>

<script>
import axios from 'axios';
    export default {
        data() {
            return {
                mobile: '',
                password: ''
            }
        },
        methods: {
            async loginForm() {
                const response = await axios.post('login', {
                    mobile: this.mobile,
                    password: this.password
                })
                console.log(response)
                localStorage.setItem('token', response.data.token)
            }
        },
    }
</script>

<style scoped>

</style>