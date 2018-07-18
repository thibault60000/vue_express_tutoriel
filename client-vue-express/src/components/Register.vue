<template>
 <div>
   <h1>Register </h1>
   <label>
     <input type="text" name="email" v-model="email" placeholder="email" /> Email </label>
   <label><input type="password" v-mode="password" name="password" placeholder="password" />Password </label>
   <button @click="register"> Register </button>
 </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      console.log('click', this.email, this.password)
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
label{
    display: block;
  }
</style>
