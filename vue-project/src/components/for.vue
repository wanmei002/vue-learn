<template>
    <table>
        <thead>
            <tr>
                <th>id</th>
                <th>name</th>
                <th>age</th>
            </tr>
        </thead>
        <tbody>
            <!-- v-for 或把当前的docment 循环渲染，加上 :key 后，如果顺序有变动  -->
            <tr v-for="(item, index) in items" :key="item.id">
                <th>{{ item.id }}</th>
                <th>{{ item.name }}</th>
                <th>{{ item.age }}</th>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    data() {
        return {
            items: [
                {
                    id: 1,
                    name: "zzh",
                    age: 18,
                },
                {
                    id: 2,
                    name: "gly",
                    age: 19,
                },
                {
                    id: 3,
                    name: "zyn",
                    age: 3,
                }
            ]
        }
    }
}
</script>
