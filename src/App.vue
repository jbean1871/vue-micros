<template>
  <div id="tiles">
    <!-- <square text="This is a square" size="small"/>
    <square text="This is a square" size="medium"/>
    <square text="This is a square" size="large"/>
    <square text="This is a square" size="large" color="#000"/> -->
    <div class="g__tile_wrapper" >
      <square
        v-for="data in records"
        v-bind:key="data.text"
        v-bind:text="data.text"
        v-bind:href="data.href"
        v-bind:description="data.description"
        v-bind:size="data.size"
        v-bind:color="data.color"
      />
    </div>
  </div>
</template>

<script>
import square from './components/square.vue'
import json from './json/data.json'

export default {
  name: 'tiles',
  data(){
    return{
      records: json.records,
      options: json.options
    }
  },
  components: {
    square
  }
}
</script>

<style src="./assets/tailwind.css"/>
<style>
.g__tile_wrapper{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  flex-direction: row;
  align-items: center;
}

</style>
