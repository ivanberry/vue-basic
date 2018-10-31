<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <input type="text" name="value" v-model="value">
    <Component v-bind:value="value" v-bind:title="title" v-bind:description="description" />
    <select v-model="selectValue" multiple v-if="options && options.length">
      <option v-for="item of options">
        {{item}}
      </option>
    </select>
    <p>{{selectValue}}</p>

    <EventTest v-bind:posts="posts" v-on:enlarge-test="eventFromChild" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Component from './components/component.vue'
import EventTest from './components/Event.vue'

export default {
  name: 'app',
  data: () => ({
    title: "你是谁",
    description: "我是你",
    value: "",
    options: [1,2,3],
    selectValue: [],
    posts: [
      {title: 'xxxx', description: 'yyyyy'},
      {title: 'xxxx', description: 'yyyyy'},
    ]
  }), 
  methods: {
    eventFromChild: (value) => {
      console.log(value)
    }
  },
  computed: {
    content: function () {
      return this.value
    }
  },
  components: {
    HelloWorld,
    Component,
    EventTest
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
