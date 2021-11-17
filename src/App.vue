<template>
  <div id="app">

    <!-- Form #1 -->
    <AppForm>
      <template v-slot:help>
        <h3>Form #1</h3>
        <p>{{ help }}</p>
      </template>
      <template v-slot:fields>
        <input type="text" placeholder="email">
        <input type="text" placeholder="username">
        <input type="password" placeholder="password">
      </template>
      <template v-slot:buttons>
        <button type="submit">Send</button>
      </template>

      <small><i>Status Message</i></small>

    </AppForm>


    <!-- Form #2 -->
    <AppForm>
      <template v-slot:help>
        <h3>Form #2</h3>
        <p>{{ help }}</p>
      </template>
      <template v-slot:fields>
        <input type="text" placeholder="name">
        <input type="text" placeholder="message">
      </template>
      <template v-slot:buttons>
        <button type="submit">Send</button>
      </template>
    </AppForm>


  </div>
</template>

<script>

import AppForm from "@/components/AppForm";

export default {
  name: 'App',
  components: {
    AppForm
  },
  data() {
    return {
      help: 'Custom App component data() for Help section'
    }
  }
}
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

input {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 6em;
}
</style>
