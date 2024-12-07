<script>
    export default {
        methods: {
            click() {
                console.log("click in comp with passed data");
            }
        },
        props: ["bgColor", "msg"],
    }
</script>

<template>
    <div class="comp">
        data from app
        <button @click="click" :style="{ backgroundColor: bgColor }">
            {{ msg }}
        </button>
    </div>
</template>

<style scoped>
    .comp {
        border: 1px blue dashed;
        padding: 1rem;
    }
</style>