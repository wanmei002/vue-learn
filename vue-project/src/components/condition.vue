<template>
    <h3>条件渲染</h3>
    <!-- if else ,字符串必须用单引号括起来 -->
    <div v-if="size === 'bbb'">size is bbb</div>
    <div v-else-if="size === 'ccc'">size is ccc</div>
    <div v-else> size default</div>
    <!-- v-show 是会渲染，只是用 display:none 隐藏了 -->
    <div v-show="flag == 'ccc'"> hello </div>
</template>

<script>
export default {
    data() {
        return {
            size: "aaa",
            flag: "ccc"
        }

    }
}

</script>