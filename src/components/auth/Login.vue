<template>
<form class="login" @submit.prevent="login(user)">
  <h3> Log In </h3>
  
  <input type="text" placeholder="username" v-model="user.username" autofocus>
  <input type="password" placeholder="password" v-model="user.password">
  
  <input type="submit" class="button" value="Begin Tour">
</form>
</template>

<script>
import { loginAction } from '../../vuex/auth/auth.actions'

export default {
  data () {
    return {
      user: {
        username: '',
        password: '',
      },
    }
  },

  vuex: {
    actions: {
      login: loginAction,
    },
  },
}
</script>

<style scoped>
.login {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  
  min-height: 300px;
  padding: 1rem;
  color: #86969C;
}

.login h3 {
  font-size: 30px;
  font-weight: 700;
}

input {
  padding: 1rem;
  margin: 1rem;
  
  border: 1px dotted #ccc;
  outline-offset: 0
}

.button {
  padding: 5px 15px;
  color: #FFF;
  background-color: #4EBBE4;
  border: 1px solid #16A2D7;
  border-radius: 4px;
  
  cursor: pointer;
}
</style>