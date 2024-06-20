<style src="../style/div.css"></style>
<template>
    <div v-bind="div">
        <div>
            姓: <input type="text" v-model="name" />
        </div>
        <div>
            名: <input type="text" v-model="age" />
        </div>
        <div>
            {{ name }} - {{ age }}
        </div>
        <div>
            fullname: {{ fullName() }}
        </div>
    </div>
</template>

<script >
export default {
    data(){
        return {
            div: {
                class: "divred"
            },
            name: "zzh",
            age: 18
        }
    },
    methods: {
        fullName(){
            console.log("method full name")
            return this.name + '-' + this.age
        }
    }
}
</script>
