<template>
  <div>
    <div v-for="item in ask" :key="item.id">{{item.title}}</div>
  </div>
</template>

<script>
import { fetchAskList } from '../api/index.js';

export default {
  data() {
    return {
      ask: []
    }
  },
  created() {
    var vm = this;
    fetchAskList()
    .then(function(response) {
      console.log('호출 후: ', this);
      vm.ask = response.data;
    })
    .catch(function(error) {
      console.log(error)
    })
  }
}
</script>

<style>

</style>