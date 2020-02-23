<template>
  <f7-page name="settings">
    <f7-navbar v-bind:title="title" back-link="Back"></f7-navbar>

    <!-- Toolbar-->
    <f7-toolbar bottom>
      <f7-link>Left Link</f7-link>
      <f7-link>Right Link</f7-link>
    </f7-toolbar>

    <!-- Page content-->
    <f7-block strong>
      <p>{{content}}</p>
    </f7-block>

  </f7-page>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Settings',
        content: 'Here are settings of the page'
      }
    }
  }
</script>
