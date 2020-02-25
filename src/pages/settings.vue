<template>
  <f7-page name="settings">
    <f7-navbar v-bind:title="title" back-link="Back"></f7-navbar>

    <!-- Toolbar-->
    <f7-toolbar bottom>
      <f7-link>Left Link</f7-link>
      <f7-link>Right Link</f7-link>
    </f7-toolbar>

    <!-- Page content-->
    <f7-block>
      <div class="card">
        <div class="card-header">Header</div>
        <div class="card-content card-content-padding">
          <p>{{content}}</p>
        </div>
        <div class="card-footer">Footer</div>
      </div>
    </f7-block>
    <f7-block>
      <f7-block-title>General application settings</f7-block-title>
      <f7-list accordion-list>
        <f7-list-item accordion-item title="General configuration">
          <f7-accordion-content>
            <f7-list>
              <f7-list-item title="Item 1"></f7-list-item>
              <f7-list-item title="Item 2"></f7-list-item>
              <f7-list-item title="Item 3"></f7-list-item>
              <f7-list-item title="Item 4"></f7-list-item>
            </f7-list>
          </f7-accordion-content>
        </f7-list-item>
        <f7-list-item accordion-item title="Alerting">
          <f7-accordion-content>
            <f7-list>
              <f7-list-item title="Item 1"></f7-list-item>
              <f7-list-item title="Item 2"></f7-list-item>
              <f7-list-item title="Item 3"></f7-list-item>
              <f7-list-item title="Item 4"></f7-list-item>
            </f7-list>
          </f7-accordion-content>
        </f7-list-item>
        <f7-list-item accordion-item title="Theming">
          <f7-accordion-content>
            <f7-list>
              <f7-list-item title="Item 1"></f7-list-item>
              <f7-list-item title="Item 2"></f7-list-item>
              <f7-list-item title="Item 3"></f7-list-item>
              <f7-list-item title="Item 4"></f7-list-item>
            </f7-list>
          </f7-accordion-content>
        </f7-list-item>
      </f7-list>
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
