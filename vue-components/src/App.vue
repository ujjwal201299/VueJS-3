<template>
  <!-- Props -->
  <Greet :name="name" :hero-name="channel" />
  <Greet name="Bruce" hero-name="Batman" />
  <Greet name="Clark" hero-name="Superman" />
  <Greet name="Diana" hero-name="Wonder Woman" />

  <Article id="article-id" title="Article title" :likes="50" :isPublished="true" />

  <!-- Provide/ Inject -->
  <h3>App component {{ name }}</h3>
  <ComponentC />

  <!-- Events -->
  <button @click="showPopup = true">Show Popup</button>
  <Popup v-show="showPopup" @close="closePopup" />
  <input type="text" v-model="newName" />
  <Input type="text" v-model="name" />

  <!-- Slots -->
  <Card></Card>
  <Card>Card Content</Card>
  <Card><h2>Card Content</h2></Card>
  <Card>
    <img src="https://picsum.photos/200" alt="" />
  </Card>

  <Card>
    <template v-slot:header>
      <h3>Header</h3>
    </template>
    <template v-slot:default>
      <img src="https://picsum.photos/200" alt="" />
    </template>
    <template v-slot:footer>
      <button>View details</button>
    </template>
  </Card>

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }} {{ slotProps.firstName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }}
    </template>
  </NameList>

  <h4>App Component</h4>
  <ChildStyles>
    <h4>ChildStyles</h4>
  </ChildStyles>

  <!-- Dynamic Components -->
  <button @click="activeTab = 'TabA'">Tab A</button>
  <button @click="activeTab = 'TabB'">Tab B</button>
  <button @click="activeTab = 'TabC'">Tab C</button>

  <!-- Keep alive is used to cache the data on changing the component -->
  <keep-alive>
    <component :is="activeTab" />
  </keep-alive>

  <!-- <TabA v-if="activeTab === 'TabA'" />
  <TabB v-if="activeTab === 'TabB'" />
  <TabC v-if="activeTab === 'TabC'" /> -->

  <!-- Teleport Component -->
  <teleport to="#portal-root">
    <Portal />
  </teleport>
</template>

<script>
import Greet from "./components/Greet";
import Article from "./components/Article";
import ComponentC from "./components/ComponentC.vue";
import Popup from "./components/Popup";
import Input from "./components/Input";
import Card from "./components/Card";
import NameList from "./components/NameList";
import ChildStyles from "./components/ChildStyles";
import TabA from "./components/TabA";
import TabB from "./components/TabB";
import TabC from "./components/TabC";
import Portal from "./components/Portal";

export default {
  name: "App",
  components: {
    Greet,
    Article,
    ComponentC,
    Popup,
    Input,
    Card,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    Portal,
  },
  data() {
    return {
      name: "Ujjwal",
      channel: "Code",
      showPopup: false,
      newName: "",
      activeTab: "TabA",
    };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log("Name: " + name);
    },
  },
  provide() {
    return {
      userName: this.name,
    };
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

h4 {
  color: orange;
}
</style>
