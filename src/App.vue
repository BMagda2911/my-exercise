<template>
  <div id="app">
    <h1>Cookie Feeder</h1>
    <label for="choose">Choose from the list to show Cookie's state:</label>
    <select id="choose" @change="selectChanged">
      <option disabled value="">Please select one</option>
      <option value="a">A</option>
      <option value="b">B</option>
      <option value="c">C</option>
    </select>
    <br>
    <label for="userInput"> or simply enter your choice: </label>
    <input type="text" name="userInput" placeholder="A, B or C" @change="selectChanged">
    <compA v-if="showA" />
    <compB v-if="showB" />
    <compC v-if="showC" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import compA from './components/compA.vue'
import compB from './components/compB.vue'
import compC from './components/compC.vue'

export default Vue.extend({
  name: 'App',
  components: {
    compA,
    compB,
    compC
  },
  data: function () {
    return {
      showA: true,
      showB: false,
      showC: false
    }
  },
  methods: {
    selectChanged (event: any) {
      console.log(event)
      const activeComponent = event.target.value
      if (activeComponent === 'a') {
        this.showA = true
        this.showB = false
        this.showC = false
      }
      if (activeComponent === 'b') {
        this.showA = false
        this.showB = true
        this.showC = false
      }
      if (activeComponent === 'c') {
        this.showA = false
        this.showB = false
        this.showC = true
      }
    }
  }
})

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#a {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#b {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#c {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
