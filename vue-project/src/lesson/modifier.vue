<style>
.red {
    width: 100px;
    height: 100px;
    background-color: red;
}
.blue {
    width: 60px;
    height: 60px;
    background-color: blue;
    margin: 2px;
}
</style>
<template>
    <button @click="showInfo($event)">show info 1</button>
    <button @click="showInfo2($event, 123)">show info 2</button>
    <div>
        <!-- 阻止默认事件 -->
        <a href="http://google.com" @click.prevent="jumpT">google.com</a>
    </div>
    <div @click="bubble1" v-bind="div1">
        div1
        <!-- .top 阻止冒泡 -->
        <div v-bind="div2" @click.stop="bubble2">
            div2
        </div>
    </div>

    <div v-bind="div1" @click.capture="showMsg(111)">
        <div v-bind="div2">
            div2
        </div>
    </div>

    
</template>
<script>
export default {
    data() {
        return {
            aa: "bbb",
            cc: "ddd",
            div1: {
                class: "red"
            },
            div2: {
                class: "blue"
            }
        }
    },
    methods: {
        showInfo(event) {
            console.log(event)
            alert("hello zzh")
        },
        showInfo2(event, number) {
            console.log(event, number)
            alert("~ hello zzh")
        },
        jumpT() {
            alert("不让你跳转")
        },
        bubble1() {
            alert("冒泡1")
        },
        bubble2() {
            alert("冒泡2")
        },
        showMsg(number){
            alert(number)
        }
    }
}
</script>