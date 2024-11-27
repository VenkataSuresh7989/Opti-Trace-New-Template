<template>
  <ion-footer v-if="getPath">
    <ion-toolbar>
      <div class="flex-footer">
        <ion-button mode="ios" class="btnerror" @click="btnExit">Exit</ion-button>
        <ion-button mode="ios" class="btnprimary" @click="btnBack">Back</ion-button>
        <ion-button mode="ios" class="btnsuccess" @click="btnContinue">Apply & Continue</ion-button>
      </div>
    </ion-toolbar>
  </ion-footer>
</template>
<script>
import eventBus from "../assets/script/eventBus";
export default {
  name: "FooterView",
  computed: {
    getPath: function() {
      return (this.$route.path != '/amplifier/selectdevice');
    }
  },
  methods: {
    btnBack: function() {
      this.$router.back();
    },
    btnContinue: function() {
      let evtName = "evtback" + this.$route.name;
      console.log("evtName", evtName);      
      eventBus().emitter.emit(evtName);
    }
  }
};
</script>
