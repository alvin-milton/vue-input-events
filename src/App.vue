<template>
  <div id="app">
    <h1>Event handling</h1>
    Can modify the value directly
    <br>
    <br>
    <button v-on:click="counter++">Click to increase counter</button>
    <br>
    <br>
    Can call a method to do the same
    <br>
    <br>
    <button v-on:click="increase">Click to increase counter</button>
    <br>
    <br>
    <div>Counter: {{ counter }}</div>
    <br>
    Both will maintain the state in this instance.
    <br>
    <br>
    @click is the shorthand way of writing v-on:click.
    <br>
    <br>
    <h2>Event Modifiers</h2>
    @click.prevent prevents the event from happening
    <br>
    <br>
    @click.stop prevents bubbling up the tree
    <br>
    <br>
    @click.once will only trigger the event listener the first time its fired
    <br>
    <br>
    @click.capture will capture the event (goes down the tree) as opposed to bubbling it.
    <br>
    <br>
    @click.self applies the event listener to the element that is calling it.
    <br>
    <br>
    You can chain the modifiers together: i.e. @click.stop.capture.once
    <br>
    <br>
    <h2>Key Modifiers</h2>
    Captures keybpard events so you can attach a handler when that key is pressed.
    <br>
    <br>
    @keyup.keyCode="methodName" is the format used for handling keyboard events. Common keys have shorthand labels so you don't have to remember the numeric key mappings.
    <br>
    <br>
    Some notable modifiers are .ctrl, .alt, .shift and .meta. The last of which stands for the Windows or Apple key on the respective machine you are using. .exact will handle key presses for when a specific key is pressed and no other, ignoring key press combinations.
    
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: () => {
    return {
      counter: 0
    }
  },
  methods: {
    increase(e) {
      // e is used to deal with event data
      this.counter++
    }
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
