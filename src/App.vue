<template>
  <div id="app">

    <h2>Animation</h2>
    <AnimatedListCss/>
    <br/>
    <hr/>
    <br/>

    <AnimatedList/>
    <br/>
    <hr/>
    <br/>

    <JsAnimation/>
    <br/>
    <hr/>
    <br/>

    <TransitionAnimation/>
    <br/>
    <hr/>
    <br/>

    <h2>Dynamic components</h2>
    <template>
      <select v-model="componentName">
        <option value="ComponentX">Component X</option>
        <option value="ComponentY">Component Y</option>
      </select>
    </template>

    <!--  Allows to dynamically load the component  -->
    <!-- component lives on memory instead of unmount  -->
    <keep-alive>
      <component :is="componentName"></component>
    </keep-alive>


    <br/>
    <hr/>
    <br/>

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


    <br/>
    <hr/>
    <br/>

    <!--  Slot properties - Vue feature  -->
    <template>

      <SlotPropComponent v-slot="v">
        <h2>App Component heading => SlotProp Component</h2>
        <p>App component with value from child component: <strong>{{ v.user.name }}</strong></p>
      </SlotPropComponent>

      <hr/>

      <SlotPropComponent #default="{user, favorites}">
        <p>Another SlotProp Component with value from child component: <strong>{{ user.name }}</strong></p>
        <ul>
          <li v-for="(item, index) in favorites"
              :key="item+index"
              :id="item+index"
          >
            {{ index }}. {{ item }}
          </li>
        </ul>
      </SlotPropComponent>

    </template>


  </div>
</template>

<script>

import AppForm from "@/components/AppForm";
import ComponentX from "@/components/ComponentX";
import ComponentY from "@/components/ComponentY";
import TransitionAnimation from "@/components/TransitionAnimation";
import JsAnimation from "@/components/JsAnimation";
import AnimatedList from "@/components/AnimatedList";
import AnimatedListCss from "@/components/AnimatedListCss";
import SlotPropComponent from "@/components/SlotPropComponent";

export default {
  name: 'App',
  components: {
    SlotPropComponent,
    AnimatedListCss,
    AnimatedList,
    JsAnimation,
    TransitionAnimation,
    ComponentY,
    ComponentX,
    AppForm
  },
  data() {
    return {
      help: 'Custom App component data() for Help section',
      componentName: "ComponentX",
      flag: false
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}

input {
  display: block;
  /*margin-left: auto;*/
  /*margin-right: auto;*/
  /*width: 6em;*/
}
</style>
