<script>
    export default {
        methods: {
            click() {
                alert("comp btn clicked");
            }
        }
    }
</script>

<template>
    <div class="comp">
        komponent
        <button @click="click">
            btn
        </button>
    </div>
</template>

<style scoped>
    .comp {
        border: 1px blue dashed;
        padding: 1rem;
    }
</style>