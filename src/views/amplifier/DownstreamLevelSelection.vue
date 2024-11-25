<template>  
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
  </template>
  
  <script>
  import { useRouter } from "vue-router";     
  import SpinControl from "../../components/SpinControl.vue";
  export default {
    name: "DownstreamLevelSelection",   
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
    }
    
  };
  </script>
  