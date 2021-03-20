<template>
  <div id="app">
    <div id="operation-bar">
      <span style="-webkit-app-region: drag">
        <font-awesome-icon icon="arrows-alt" />
      </span>
      <span @click="closeWindow">
        <font-awesome-icon icon="times" />
      </span>
    </div>
  </div>
</template>

<script>
const { ipcRenderer } = require('electron');

export default {
  name: 'App',
  methods: {
    closeWindow() {
      ipcRenderer.send('close-all');
    },
  },
};
</script>

<style scoped lang="scss">
#operation-bar {
  display: flex;
  justify-content: space-between;
  font-size: 20px;
}
</style>
