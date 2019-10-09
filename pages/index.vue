<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">nuxt2</h1>
      <h2 class="subtitle">My badass Nuxt.js project</h2>
      <h3>{{request.data}}</h3>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
      </div>
      <button @click="fetchSomething">Test</button>
    </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import TestMessage from "@/components/TestMessage";
import axios from "axios";

export default {
  data() {
    return { request: "" };
  },
  methods: {
    async fetchSomething() {
      console.log("test");
      this.request = await axios.get("http://icanhazip.com");
    }
  },
  components: {
    Logo,
    TestMessage
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
