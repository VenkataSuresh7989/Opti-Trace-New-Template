<template>  
<ion-page>
    <ion-content class="ion-padding main-content">
    <div class="card auto">
        <h5 class="cardtitle">Downstream Levels</h5>  
        <div class="customradio full">
            <ion-radio-group value="trunk">                             
                <ion-radio value="trunk">Trunk</ion-radio>                
            </ion-radio-group>
        </div> 
        <h5 class="cardtitle">Trunking pad Value</h5>    
        <SpinControl />
        <SpinControl />        
        <div class="setBtn center">
            <ion-button class="btnprimary" mode="ios"><span> Set</span></ion-button>
        </div>
    </div>  
    </ion-content>
    </ion-page>
  </template>
  
  <script>
  import { useRouter } from "vue-router";     
  import eventBus from '../../assets/script/eventBus';   
  import SpinControl from "../../components/SpinControl.vue";
  export default {
    name: "TrunkLevelDetailView",   
    data(){
        return{             
        }        
      },          
    setup() {
      const router = useRouter();      
      return {       
        router,
      };
    },
    components:{
        SpinControl
    },
    mounted() {
      eventBus().emitter.on("evtbackTrunkLevelDetailView",()=>{
        this.$router.push("../amplifier/guidedconfigfile");
      });
    },
    unmounted() {
      eventBus().emitter.off("evtbackTrunkLevelDetailView");
    },
    
  };
  </script>
  