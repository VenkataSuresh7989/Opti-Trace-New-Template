<template>
  <ion-app v-if="isLogin">
    <WelcomeScreen v-show="isWelcome"  />
    <ConnectionType v-show="isConType" />
    <Login v-show="isLoginScreen" />
  </ion-app>
  <ion-app v-else >
    <!-- Side Menu -->
    <Sidemenu />

    <!-- Header Content -->
    <HeaderView />

    <!-- Main Content -->
    <ion-content id="main-content">
      <ion-router-outlet :animated="false" />
    </ion-content>

    <!-- Footer -->
    <FooterView />
  </ion-app>
</template>

<script>
import WelcomeScreen from "./components/WelcomeScreen.vue";
import ConnectionType from "./components/ConnectionType.vue";
import Login from "./components/LoginScreen.vue";
import Sidemenu from "./components/SideMenu.vue";
import HeaderView from "./components/HeaderView.vue";
import FooterView from "./components/FooterView.vue";
import eventBus from "./assets/script/eventBus";
import { useRouter } from "vue-router";

export default {
  name: "App",
  data() {
    return {
      isWelcome: true,
      isConType: false,
      isLoginScreen: false,
    };
  },
  components: {
    Login,
    Sidemenu,
    HeaderView,
    FooterView,
    WelcomeScreen,
    ConnectionType
  },
  setup() {
    const router = useRouter();
    return {
      router,
    };
  },
  computed: {
    isLogin() {
      let resp = localStorage.getItem("isLogin");
      return resp == undefined || resp == null ? true : false;
    },
  },
  created() {
    setTimeout(() => {
      this.isWelcome = false;
      this.isConType = true;
    }, 3000);
  },
  mounted() {    
    eventBus().emitter.on("evtconnectiontype",()=>{
      console.log("Test");
      
      this.isConType = false;
      this.isLoginScreen = true;
    });
    eventBus().emitter.on("evtbtnback",()=>{
      this.isLoginScreen = false;
      this.isConType =  true;
    });

  },
  unmounted() {
    // eventBus().emitter.off("evtconnectiontype");
    eventBus().emitter.off("evtbtnback");
  }
};
</script>
