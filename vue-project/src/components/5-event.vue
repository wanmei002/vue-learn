<template>
    <h3>
        事件修饰符
    </h3>
    <div @click="dClick">
        <!-- 事件修饰符 ,stop阻止冒泡  prevent组织默认事件  enter 阻止按键事件， once执行一次事件  -->
        <p @click.stop="pClick">this is p</p>
    </div>
</template>

<script>
export default {
    methods: {
        pClick() {
            console.log("p click");
        },
        dClick() {
            console.log("d click")
        }
    }
}
</script>