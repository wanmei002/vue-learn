<template>
    <div>
        <div>{{ aa }}</div>
        <h4>add {{ 1 + 1 }}</h4>
        <h4>options: {{ $options }}</h4>
        <h4>emit: {{ $emit }}</h4>
        <h4>_c: {{ _c }}</h4>
    </div>
</template>

<script>
export default {
    data() {
        return {
            aa: "bb"
        }
    },
}
</script>