<template>
    <!-- 对象 -->
    <p :class="{ 'active': isActive, 'text-danger': hasError }"> class 1</p>
    <!-- 直接对象 -->
    <p :class="classObj">class 2</p>
    <!-- 数组 -->
    <p :class="[arrActive, arrHasError]">class 3</p>
    <!-- 三元运算符 -->
    <p :class="[isActive ? 'active' : '']">class 4</p>
    <!-- 数组里面嵌套对象 -->
    <p :class="[{ 'active': true }, arrActive]"></p>
</template>

<style>
.active {
    font-size: 20px;
}

.text-danger {
    color: red;
}
</style>

<script>
export default {
    data() {
        return {
            isActive: true,
            hasError: true,
            classObj: {
                'active': true,
                'text-danger': true,
            },
            arrActive: 'active',
            arrHasError: 'text-danger',
        }
    }

}
</script>