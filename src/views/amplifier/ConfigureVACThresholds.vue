<template>
    <div class="card auto">
      <h5 class="cardtitle">Configure VAC Thresholds</h5>


      <h6 class="subtitle mb-10">Alarm Thresholds</h6>
      <div class="custominput noicon">                                    
          <ion-input label-placement="stacked" placeholder="123456" required mode="ios" value="123456">
              <div slot="label">Amp ID</div>
          </ion-input>             
      </div>  
      <div class="custominput noicon mb-10">                                     
          <ion-input label-placement="stacked" placeholder="Enter value" required value="37.4" mode="ios">
              <div slot="label">Low Limit(V)</div>
          </ion-input>             
      </div>  
      <div class="setBtn center">
        <ion-button class="btnprimary" mode="ios"><span> Set</span></ion-button>
      </div>

      <div class="ion-margin-top">
        <h6 class="subtitle mb-10">Warning Thresholds</h6>
        <div class="custominput noicon">                                    
            <ion-input label-placement="stacked" placeholder="123456" required mode="ios" value="123456">
                <div slot="label">Amp ID</div>
            </ion-input>             
        </div>  
        <div class="custominput noicon mb-10">                                     
            <ion-input label-placement="stacked" placeholder="Enter value" required value="37.4" mode="ios">
                <div slot="label">Low Limit(V)</div>
            </ion-input>             
        </div>  
        <div class="setBtn center">
          <ion-button class="btnprimary" mode="ios"><span> Set</span></ion-button>
        </div>
      </div>
      
    </div>
  </template>
  
  <script>
  import { useRouter } from "vue-router";
  import SpinControl from "../../components/SpinControl.vue";
  
  export default {
    name: "ConfigureVACThresholds",
    data(){
        return{
          togglechk:false,
        }        
      },
      components:{
        SpinControl
      }, 
    setup() {
      const router = useRouter();
      return {        
        router,
      };
    },
  };
  </script>
  