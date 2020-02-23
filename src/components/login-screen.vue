<template>
  <f7-login-screen id="my-login-screen">
    <f7-view>
      <f7-page login-screen>
        <f7-login-screen-title>Login</f7-login-screen-title>
        <f7-list form>
        <f7-list-input
            type="text"
            name="username"
            placeholder="Your username"
            :value="username"
            @input="username = $event.target.value"
        ></f7-list-input>
        <f7-list-input
            type="password"
            name="password"
            placeholder="Your password"
            :value="password"
            @input="password = $event.target.value"
        ></f7-list-input>
        </f7-list>
        <f7-list>
        <f7-list-button title="Sign In" @click="alertLoginData"></f7-list-button>
        <f7-block-footer>
            Some text about login information.<br>Click "Sign In" to close Login Screen
        </f7-block-footer>
        </f7-list>
      </f7-page>
      </f7-view>
  </f7-login-screen>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    alertLoginData() {
      this.$f7.dialog.alert('Username: ' + this.username + '<br>Password: ' + this.password, () => {
        this.$f7.loginScreen.close();
      });
    }
  },
}
</script>
