<style scoped>
.base {
  width: 17%;
  height: 17%;
  background-color: #aaa;
}
.red {
  background-color: red;
}
.blue {
  background-color: grey;
}
.border {
  border: 1px solid black;
}
</style>
<template>
<div :class="classA">classA</div>
<div :class="classObj">class obj</div>
<div :class="classArr">class arr</div>
</template>

<script scoped>
export default {
  data(){
    return {
      classA: "base",
      classObj : {
        base: true,
        red: true,
        blue: false
      },
      classArr: [
          "base", "blue", "border"
      ]
    }
  },
}
</script>
