<template>

</template>

<script scoped>
var data = {
  name: "zzh",
  address: "shanghai"
}



function Observer(obj) {
  const keys = Object.keys(obj)
  console.log("keys ", keys)
  for (let key of keys) {
    Object.defineProperty(this, key, {
      get(){
        console.log("get")
        return obj[key]
      },
      set(val){
        console.log("set ", val)
        obj[key] = val
      }
    })
  }
}

let obs = new Observer(data)
console.log("obs: ", obs)

function changeObs(){
  obs.name = "zyn"
}

console.log("data: ", data)
console.log("obs: ", obs)

</script>
