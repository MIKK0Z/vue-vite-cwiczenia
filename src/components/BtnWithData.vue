<script>
    export default {
        methods: {
            click() {
                console.log("click in comp");
            }
        }
    }
</script>

<template>
    <div class="comp">
        data in comp
        <button @click="click">
            btn in comp
        </button>
    </div>
</template>

<style scoped>
    .comp {
        border: 1px blue dashed;
        padding: 1rem;

        & > button {
            background-color: blue;
            color: white;
        }
    }
</style>