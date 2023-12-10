<template>
    <!-- click 可以直接调用 methods里面的方法，methods 里面可以
        使用 this 来获取data 里面的数据
    -->
    <div :class="dC" @click="count">{{ countNum }}</div>
    <!-- 如果要传 event 参数 可以在最后一个参数里面传递 $event -->
    <p v-for="(item, index) in items" @click="count(id, $event)"> {{ item.id }} ---- {{ item.name }} </p>
</template>

<script>
export default {
    data() {
        return {
            dC: "aaaa",
            countNum: 0,
            items: [
                { id: 1, name: "zzh", age: 10 },
                { id: 2, name: "zyn", age: 11 }
            ]
        }
    },

    methods: {
        // e 表示 event
        count(id, e) {
            console.log(e);
            // this 可以直接获取 data 里的数据
            this.countNum++
        }
    }
}
</script>

<style>
.aaaa {
    width: 200px;
    height: 200px;
    background-color: #ddd;
    /* coff; */
}
</style>

