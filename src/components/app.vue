<template>
<f7-app :params="f7params" theme-dark>

  <!-- Left panel with cover effect when hidden -->
  <f7-panel left cover theme-dark :visible-breakpoint="960">
    <f7-view>
      <f7-page>
        <f7-navbar title="Navigation"></f7-navbar>
        <!--<f7-block-title>Left View Navigation</f7-block-title>
        <f7-list>
          <f7-list-item link="/left-page-1/" title="Left Page 1"></f7-list-item>
          <f7-list-item link="/left-page-2/" title="Left Page 2"></f7-list-item>
        </f7-list>-->
        <f7-block-title>CONSOLE</f7-block-title>
        <f7-list>
          <f7-list-item link="/home/" view=".view-main" panel-close title="Home"></f7-list-item>
          <f7-list-item link="/trackers/" view=".view-main" panel-close title="Trackers"></f7-list-item>
          <f7-list-item link="/settings/" view=".view-main" panel-close title="Settings"></f7-list-item>
          <!-- <f7-list-item link="#" view=".view-main" back panel-close title="Back in history"></f7-list-item> -->
        </f7-list>
        <f7-block-title>HELP</f7-block-title>
        <f7-list>
          <f7-list-item link="/about/" view=".view-main" panel-close title="Help"></f7-list-item>
          <f7-list-item link="/about/" view=".view-main" panel-close title="Documentation"></f7-list-item>
          <f7-list-item link="/about/" view=".view-main" panel-close title="About"></f7-list-item>
        </f7-list>
      </f7-page>
    </f7-view>
  </f7-panel>


  <!-- Right panel with reveal effect-->
  <f7-panel right reveal theme-dark>
    <f7-view>
      <f7-page>
        <f7-navbar title="Right Panel"></f7-navbar>
        <f7-block>Right panel content goes here</f7-block>
      </f7-page>
    </f7-view>
  </f7-panel>


  <!-- Your main view, should have "view-main" class -->
  <f7-view main class="safe-areas" url="/"></f7-view>


  <!-- Popup -->
  <f7-popup id="my-popup">
    <f7-view>
      <f7-page>
        <f7-navbar title="Popup">
          <f7-nav-right>
            <f7-link popup-close>Close</f7-link>
          </f7-nav-right>
        </f7-navbar>
        <f7-block>
          <p>Popup content goes here.</p>
        </f7-block>
      </f7-page>
    </f7-view>
  </f7-popup>

  <login-screen></login-screen>

</f7-app>
</template>
<script>
  import { Device }  from '../js/framework7-custom.js';
  import cordovaApp from '../js/cordova-app.js';
  import routes from '../js/routes.js';
  import LoginScreen from '../components/login-screen';

  export default {
    data() {
      return {
        // Framework7 Parameters
        f7params: {
          id: 'io.digitalean.incub.alterting', // App bundle ID
          name: 'Alerting', // App name
          theme: 'auto', // Automatic theme detection


          // App routes
          routes: routes,

          // Register service worker
          serviceWorker: Device.cordova ? {} : {
            path: '/service-worker.js',
          },
          // Input settings
          input: {
            scrollIntoViewOnFocus: Device.cordova && !Device.electron,
            scrollIntoViewCentered: Device.cordova && !Device.electron,
          },
          // Cordova Statusbar settings
          statusbar: {
            iosOverlaysWebView: true,
            androidOverlaysWebView: false,
          },
        },

        // Login screen data
        username: '',
        password: '',
      }
    },
    components: {
      'login-screen': LoginScreen
    },
    methods: {
      alertLoginData() {
        this.$f7.dialog.alert('Username: ' + this.username + '<br>Password: ' + this.password, () => {
          this.$f7.loginScreen.close();
        });
      }
    },
    mounted() {
      this.$f7ready((f7) => {
        // Init cordova APIs (see cordova-app.js)
        if (Device.cordova) {
          cordovaApp.init(f7);
        }
        // Call F7 APIs here
      });
    }
  }
</script>
