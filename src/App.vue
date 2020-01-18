<template>
  <div id="app">
    <Chmod v-on:bit-change="generateFlags"/>
    <Ls :flags="flags"/>
    <p>$ _</p>
  </div>
</template>

<script>
import Chmod from './components/Chmod.vue'
import Ls from './components/Ls.vue'

export default {
  name: 'app',
  components: {
    Chmod,
    Ls
  },
  data() {
    return {
      flags: {
        owner: 'rwx',
        group: 'rwx',
        others: 'rwx'
      },
      mapsBits: {
        '000': '---',
        '001': '--x',
        '010': '-w-',
        '011': '-wx',
        '100': 'r--',
        '101': 'r-x',
        '110': 'rw-',
        '111': 'rwx',
      },
      mapsNumbers: ['000', '001', '010', '011', '100', '101', '110', '111']
    }
  },
  methods: {
    generateFlags(e) {
      const splits = e.split('').map(i => parseInt(i));
      const splitMap = splits.map(s => this.mapsNumbers[s]);
      this.flags = {
        owner: this.mapsBits[splitMap[0]],
        group: this.mapsBits[splitMap[1]],
        others: this.mapsBits[splitMap[2]],
      }
    }
  }
}
</script>

<style>
#app {
  text-align: left;
  margin-top: 60px;
  font-size: 18px;
}
</style>
