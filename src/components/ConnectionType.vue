<template>
    <ion-page>
      <div class="wrapper">
        <div class="toparea">
            <h3 class="heading">Connection Type <span>Select Wi-Fi or Bluetooth</span></h3>
        </div>        
        <div class="middlearea" style="height: calc(100vh - 150px);">
            <div class="card center about">
                <ion-segment value="default" mode="ios" class="sm">
                    <ion-segment-button value="default" mode="ios">
                      <ion-label class="icon-label"><span class="svgicon" v-html="$store.state.wifi"></span> <span class="svglabel">Wi-Fi</span> </ion-label>
                      </ion-segment-button>
                      <ion-segment-button value="segment">
                      <ion-label><span class="svgicon" v-html="$store.state.bluetooth"></span> <span class="svglabel"> Bluetooth</span></ion-label>
                    </ion-segment-button>                    
                </ion-segment>

                
                <ion-select label="Select Device" label-placement="stacked" interface="action-sheet" placeholder="CADA-TS1">
                    <ion-select-option value="0">CADA-TS1</ion-select-option>
                    <ion-select-option value="1">CADA-M3</ion-select-option>
                    <ion-select-option value="2">EMBED-JIO</ion-select-option>
                </ion-select>               
                
                <div class="flex-box space-between">
                  <ion-button class="btnprimary sm" mode="ios" id="open-custom-dialog">
                    <span class="svgicon" v-html="$store.state.sync"></span> Scan
                  </ion-button>

                  
                    <ion-modal id="example-modal" ref="modal" trigger="open-custom-dialog">
                      <div class="modalWrapper">
                        <div class="modalIcontype info">                          
                            <span class="svgicon" v-html="$store.state.infoicon"></span>                          
                        </div>
                        <div class="modalInfo">
                          <p class="mt-0">Confirm that the trunking pad value installed in the amplifier port matches the value entered in the Guided Setup</p>
                        </div>                        
                        <div class="modalBtns flex-box space-between">
                          <ion-button class="sm warning" mode="ios" >Discard</ion-button>                          
                          <ion-button class="sm success" mode="ios" >Save</ion-button>
                          <ion-button class="sm error" mode="ios" >Cancel</ion-button>
                        </div>
                      </div>
                    </ion-modal>
                  <ion-button class="btnprimary sm" @click="btnConClick()" mode="ios">
                    <span class="svgicon"></span> Connect
                  </ion-button>
                </div>
            </div>
        </div>
      </div>
    </ion-page>  
  </template>
  
  <script>
  import { useRouter } from 'vue-router';
  import eventBus  from '../assets/script/eventBus';
  
  export default {
    name: "ConnectionType",
    setup() {
      const router = useRouter();
      return {
        router,
      };
    },
    methods: {
      btnConClick() {
        eventBus().emitter.emit("evtconnectiontype");
      },
    },
  }
  </script>