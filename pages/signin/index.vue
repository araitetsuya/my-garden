<template>
  <div class="sign-in">
    <h2>Login</h2>
    <form @submit.prevent="signIn">
      <input type="text" placeholder="email" v-model="email" />
      <input type="password" placeholder="password" v-model="password" />
      <button>Sign in</button>
    </form>
    <p>
      You don't have an account?
      <router-link to="/sign_up">create account now!!</router-link>
    </p>
  </div>
</template>

<script>
  import firebase from 'firebase'

  export default {
    data() {
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      signIn: function() {
        firebase
          .auth()
          .signInWithEmailAndPassword(this.email, this.password)
          .then(user => {
            console.log(user);
            alert('Success!');
            this.$router.push('/secret');
          })
          .catch(err => {
            alert(err.message);
          })
      }
    }
  }
</script>

<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

  .sign-in {
    margin-top: 20px;

    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
  }

  input {
    margin: 10px 0;
    padding: 10px;
  }
</style>
