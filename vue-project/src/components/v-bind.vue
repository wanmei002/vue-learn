<template>
  <!-- 绑定前面需要加 : 或者 v-bind:, 这样vue才会给它赋值 -->
  <div :class="diyClass"> hello zzh </div>
  <div :id="diyID">hello diyID</div>
  <!-- 也可以直接绑定对象 里面的key就是属性名字，val就是属性值 -->
  <div v-bind="objAttr"> v-bind objAttr </div>
</template>

<script>
export default {
  data() {
    return {
      diyClass: "diyCls",
      diyID: "diyid",
      objAttr: {
        hClass: "hclass",
        hID: "hid"
      }
    }
  }
}
</script>

<style>
.diyCls {
  background: red;
  width: 200px;
  height: 300px;
}

#diyid {
  width: 200px;
  height: 200px;
  background-color: #333;
}
</style>


