<!-- 计算属性 computed, 计算属性会缓存，只会计算一次(如果没有变化的话)  methods 每次都是执行 -->
<template>
    <div>{{ lenNotZero }}</div>
</template>


<script>
export default {
    data() {
        return {
            content: ["zzh", 'gly', 'zyn'],
            obj: {
                content: ['zzh', 'gly']
            }
        }
    },
    computed: {
        lenNotZero() {
            return this.content.length > 0 ? 'Yes' : 'No'
        }
    }
}
</script>