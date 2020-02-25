<template>
  <f7-page name="trackers">
    <f7-navbar v-bind:title="title" back-link="Back"></f7-navbar>

    <!-- Toolbar-->
    <f7-toolbar bottom>
      <f7-link>Left Link</f7-link>
      <f7-link>Right Link</f7-link>
    </f7-toolbar>

    <!-- Page content-->
    <f7-block strong>
      <f7-row>
        <f7-col>50% (.col)</f7-col>
        <f7-col>50% (.col)</f7-col>
      </f7-row>
      <f7-row>
        <f7-col>50% (.col)</f7-col>
        <f7-col>{{content}}</f7-col>
      </f7-row>
    </f7-block>

  </f7-page>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Trackers',
        content: 'Here is the content of the view'
      }
    }
  }
</script>
