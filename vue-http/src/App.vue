<template>
  <CreatePost />
  <PostList />
  <hr />

  <!-- Lifecycle Hooks -->
  <Parent />
  <hr />

  <!-- Template Refs -->
  <TemplateRef />
  <hr />

  <!-- mixins -->
  <ClickCounter />
  <HoverCounter />
</template>

<script>
import PostList from "./components/PostList";
import CreatePost from "./components/CreatePost";
import Parent from "./components/Parent";
import TemplateRef from "./components/TemplateRef";
import ClickCounter from "./components/ClickCounter";
import HoverCounter from "./components/HoverCounter";

export default {
  name: "App",
  components: {
    PostList,
    CreatePost,
    Parent,
    TemplateRef,
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
