<style src="../style/div.css"></style>
<template>
    <div>
        <input type="text" v-model="name" />
        <input type="text" v-model="age" />
    </div>
    <div>
        <input type="text" v-model="fullName">
    </div>
    <div>
        <button @click="changeFullName">change full name</button>
    </div>
</template>

<script scoped>
export default {
    data() {
        return {
            name: "zzh",
            age: "18"
        }
    },
    computed: {
        fullName: {
            get() {
                console.log("get 被调用了")
                return this.name + '-' + this.age
            },
            set(value) {
                console.log("set 被调用了", value)
                const arr = value.split('-')
                this.name = arr[0]
                this.age = arr[1]
            }
        }
    },
    methods: {
        changeFullName(){
            this.fullName = "hello-19"
        }
    }
}
</script>
