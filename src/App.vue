<template>
  <div id="app">
    <tabs :value='tabValue' 
      @change='handleChangeTab'
    > 
      <tab 
        label='tab1'
        index='1'
        >
        <p>111</p>
      </tab>
      <tab index='2'>
        <span slot="label">tab2</span>
        
        <p>333</p>
      </tab>
    </tabs>
  </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      tabValue: '1'
    }
  },
  components: {
  },
  methods: {
    handleChangeTab(value) {
      this.tabValue = value;
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
