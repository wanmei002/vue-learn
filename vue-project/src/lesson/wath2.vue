<template>
<h4>{{weather}}</h4>
<div>
  <button @click="changeWeather">change weather</button>
</div>
  <h4>{{numbers}}</h4>
  <div>
    <button @click="changeNumber">change number</button>
  </div>
  <div>
    <button @click="changeNumberA"> change number a</button>
  </div>
</template>

<script scoped>
export default {
  data(){
    return {
      isHot: false,
      numbers: {
        a: 1,
        b:2,
        d: {
          dd: 3
        }
      }
    }
  },


  computed: {
    weather: {
      get(){
        return this.isHot ? '炎热' : '清凉'
      }
    }
  },

  methods: {
    changeWeather(){
      this.isHot = !this.isHot
    },
    changeNumber: function (){
      this.numbers = {a:2,b:3}
    },
    changeNumberA: function (){
      this.numbers.a++
    }
  },

  watch: {
    isHot: {
      immediate: true,
      handler(newVal, oldVal){
        console.log("in is hot watch")
        console.log(newVal, oldVal)
      }
    },
    numbers: {
      deep: true,
      handler(newVal, oldVal){
        console.log("change numbers", newVal, oldVal)
      }
    },
  }
}
</script>