<template>  
    <div class="card auto">
        <h5 class="cardtitle">Select Auxilary Plug-in</h5>

        <div class="customradio full">
            <ion-radio-group value="jmp">                            
                <ion-radio value="jmp">JMP</ion-radio>            
                <ion-radio value="2way">2-Way</ion-radio>            
                <ion-radio value="dc08">DC-08</ion-radio>
                <ion-radio value="dc10">DC-10</ion-radio>
                <ion-radio value="dc12">DC-12</ion-radio>
            </ion-radio-group>
        </div>      
    </div>  
  </template>
  
  <script>
  import { useRouter } from "vue-router";     
  export default {
    name: "AuxilaryPluginSelection",   
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
  