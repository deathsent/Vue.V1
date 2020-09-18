<template>
  <div class="about">
    <h1>Example</h1>
    <button id="count" @click="count++">Count++</button>
    <button @click="onClick()">Count--</button><br>
    <span>{{count}}</span>
  </div>
</template>

<script>
export default {
  name:"abount",
  data() {
    return {
      count:0
    }
  },
  methods:{
    onClick(){
      this.count=this.count - 1
    }
    
  }
}
</script>

<style>

</style>