<template>
  <div id="app">
    <header>
      <h1>Modular modals in Vue from scratch</h1>
      <p>
        Click one of the buttons to open corresponding popup or click popup
        backdrop to close it
      </p>
    </header>

    <main>
      <div class="control" @click="isSignInModalOpen = true">
        <button>
          Sign in
        </button>
      </div>
      <div class="control" @click="isSignUpModalOpen = true">
        <button>
          Sign up
        </button>
      </div>
    </main>

    <modal v-show="isSignInModalOpen" @close="isSignInModalOpen = false">
      <sign-in-form />
    </modal>

    <modal v-show="isSignUpModalOpen" @close="isSignUpModalOpen = false">
      <sign-up-form />
    </modal>
  </div>
</template>

<script>
import { Modal, SignInForm, SignUpForm } from './components'

export default {
  name: 'App',

  components: {
    Modal,
    SignInForm,
    SignUpForm
  },

  data() {
    return {
      isSignInModalOpen: false,
      isSignUpModalOpen: false
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
}

body {
  margin: 0;
  background-color: #f5f5f5;
}

button {
  padding: 1em;
  border: none;
  border-radius: 0.5em;
  background-color: #6fa9d6;
  color: #fff;
  cursor: pointer;
}

button:hover {
  background-color: #4a8dc1;
}

#app {
  width: 600px;
  height: 100vh;
  margin: 0 auto;
  padding: 2em 4em;
  background-color: #fff;
}

header {
  margin-bottom: 3em;
}

main {
  display: flex;
}

.control:not(:last-child) {
  margin-right: 1em;
}
</style>
