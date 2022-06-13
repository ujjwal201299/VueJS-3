<template>
  <Data />
  <hr />
  <DemoOne />
  <hr />
  <DemoTwo />
  <hr />
  <Methods />
  <hr />
  <VModel />
  <hr />
  <Computed />
  <hr />
  <Watch />
  <hr />
  <ProvideInject />
  <hr />
  <LifecycleO />
  <LifecycleC />
  <hr />
  <TemplateRef />
  <hr />
  <Person />
  <hr />
  <ClickCounter />
  <HoverCounter />
</template>

<script>
import Data from "./components/Data";
import DemoOne from "./components/DemoOne";
import DemoTwo from "./components/DemoTwo";
import Methods from "./components/Methods";
import VModel from "./components/VModel";
import Computed from "./components/Computed";
import Watch from "./components/Watch";
import ProvideInject from "./components/ProvideInject";
import LifecycleO from "./components/LifecycleO.vue";
import LifecycleC from "./components/LifecycleC.vue";
import TemplateRef from "./components/TemplateRef.vue";
import Person from "./components/Person.vue";
import ClickCounter from "./components/ClickCounter.vue";
import HoverCounter from "./components/HoverCounter.vue";

export default {
  name: "App",
  components: {
    Data,
    DemoOne,
    DemoTwo,
    Methods,
    VModel,
    Computed,
    Watch,
    ProvideInject,
    LifecycleO,
    LifecycleC,
    TemplateRef,
    Person,
    ClickCounter,
    HoverCounter,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
