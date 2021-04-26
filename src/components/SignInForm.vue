<template>
  <form class="form" @submit="onSubmitForm">
    <div class="field">
      <input type="text" placeholder="Login" id="login" />
    </div>
    <div class="field">
      <input type="password" placeholder="Password" id="password" />
    </div>
    <div class="field">
      <button class="button" type="submit">Submit</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'SignUpForm',

  methods: {
    onSubmitForm(e) {
      e.preventDefault()
    }
  }
}
</script>

<style>
.field:not(:last-child) {
  margin-bottom: 2em;
}

.field * {
  width: 100%;
}

.field input {
  padding: 0.5em 0;
  border: none;
  border-bottom: 1px solid #00000042;
}
</style>
