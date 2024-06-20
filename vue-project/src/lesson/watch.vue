<template>
<h4> {{ hotName }} </h4>
  <button @click="changeHot">change hot</button>
</template>

<script socped>
    export default {
        data(){
            return {
                isHot: false
            }
        },
        methods: {
            changeHot(){
                this.isHot = !this.isHot
            }
        },
        computed: {
            hotName: {
                get(){
                    return this.isHot ? "炎热" : "清凉"
                }
            }
        },
        watch: {
            isHot: {
                immediate: true,
                handler(newValue, oldValue) {
                  console.log("is host have be change")
                  console.log("new value", newValue)
                  console.log("old value", oldValue)
                }
            }
        }
    }
</script>
