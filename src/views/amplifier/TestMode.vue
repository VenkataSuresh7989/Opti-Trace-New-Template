<template>  
<ion-page>
  <ion-content class="ion-padding main-content">
    <div class="middlearea">
     <div class="card">
        <h5 class="cardtitle">Mode Selection</h5>

        <ion-row class="mt-15 ">
            <ion-col size-sm="8">
                <h5 class="cardtitle">Test Mode</h5>
            </ion-col>
            <ion-col size-sm="4">
                <ion-toggle :checked="togglechk" justify="end"></ion-toggle>
            </ion-col>
        </ion-row>
      </div>
    </div> 
  </ion-content> 
  </ion-page>
  </template>
  
  <script>
  import { useRouter } from "vue-router";     
  export default {
    name: "TestMode",   
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
    
  };
  </script>
  