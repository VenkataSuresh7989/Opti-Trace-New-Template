<template>
    <ion-page>
      <ion-content class="ion-padding main-content">
      <div class="middlearea">
       <div class="card">
          <ion-list class="devicelist menu" mode="ios">
            <ion-item @click="navcadagenera">
              <ion-label>
                <div>
                  <span class="device-icon sm" v-html="$store.state.layers"></span>
                  <span class="device-name">General</span>
                  <span class="angle-icon" v-html="$store.state.angleright"></span>            
                </div>                    
              </ion-label>
            </ion-item>
            <ion-item @click="navwifisettings">
              <ion-label>
                <div>
                  <span class="device-icon sm" v-html="$store.state.wifi"></span>
                  <span class="device-name">Wi-Fi Settings</span>
                  <span class="angle-icon" v-html="$store.state.angleright"></span>            
                </div>                    
              </ion-label>
            </ion-item>            
          </ion-list>
        </div>
      </div>
    </ion-content>
    </ion-page>  
    </template>
    
    <script>
    import { useRouter } from "vue-router";   
    
    export default {
      name: "CadaMenu",
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
      methods:{      
        navcadagenera: function(){
          this.$router.push("../cada/testmode");
        },
        navwifisettings: function(){
          this.$router.push("../cada/deviceinformation");
        }
      }
    };
    </script>
    