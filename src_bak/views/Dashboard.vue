<template>
  <ion-page v-show="false">
    <div class="wrapper">
      <div class="card">
        <div class="devices"></div>
      </div>    
    </div>    
  </ion-page>
  <!-- <SelectDevice v-show="false" />   -->
  <!-- <ConnectionEstablished v-show="false" /> -->
  <!-- <MainMenu /> -->
  <!-- <HealthStatus v-show="false" /> -->
  <!-- <DeviceConfiguration /> -->
  <!-- <DownstreamConfiguration /> -->
  <!-- <UpstreamConfiguration v-show="false" /> -->
  <!-- <AdvancedDiagnostics v-show="false" /> -->
  <!-- <Utilities v-show="false" /> -->
  <!-- <Profiles v-show="false" /> -->
  <!-- <SpectrumDisplay v-show="false" /> -->
  <!-- <IngressControlSwitch  v-show="false" /> -->
  <!-- <FirmwareUpgade /> -->
  <!-- <TestMode /> -->
  <!-- <AuxilaryPluginSelection /> -->
  <!-- <PortDefinition /> -->
  <!-- <DownstreamLevelSelection /> -->
  <ConfigureVACThresholds />

</template>

<script>

import { useRouter } from "vue-router";
import SelectDevice from "./SelectDevice.vue";
import ConnectionEstablished from "./ConnectionEstablished.vue";
import MainMenu from "./MainMenu.vue";
import HealthStatus from "./amplifier/HealthStatus.vue";
import DeviceConfiguration from "./amplifier/DeviceConfiguration.vue";
import DownstreamConfiguration from "./amplifier/DownstreamConfiguration.vue";
import UpstreamConfiguration from "./amplifier/UpstreamConfiguration.vue";
import AdvancedDiagnostics from "./amplifier/AdvancedDiagnostics.vue";
import Utilities from "./amplifier/Utilities.vue";
import Profiles from "./amplifier/Profiles.vue";
import SpectrumDisplay from "../components/SpectrumDisplay.vue";
import IngressControlSwitch from "./amplifier/IngressControlSwitch.vue";
import FirmwareUpgade from "./amplifier/FirmwareUpgade.vue";
import TestMode from "./amplifier/TestMode.vue";
import AuxilaryPluginSelection from "./amplifier/AuxilaryPluginSelection.vue";
import PortDefinition from "./amplifier/PortDefinition.vue";
import DownstreamLevelSelection from "./amplifier/DownstreamLevelSelection.vue";
import ConfigureVACThresholds from "./amplifier/ConfigureVACThresholds.vue";


export default {
  name: "Dashboard",
  setup() {
    const router = useRouter();
    return {
      router,
    };
  },
  components: {
    SelectDevice,
    ConnectionEstablished,
    MainMenu,
    HealthStatus,
    DeviceConfiguration,
    DownstreamConfiguration,
    UpstreamConfiguration,
    AdvancedDiagnostics,
    Utilities,
    Profiles,
    SpectrumDisplay,
    IngressControlSwitch,
    FirmwareUpgade,
    TestMode,
    AuxilaryPluginSelection,
    PortDefinition,
    DownstreamLevelSelection,
    ConfigureVACThresholds
  }
};
</script>
