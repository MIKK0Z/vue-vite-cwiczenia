<script>
    export default {
        props: ["elements"],
    }
</script>

<template>
    <div class="comp">
        data from app
        <select>
            <option v-for="el in elements" :key="el">{{ el }}</option>
        </select>
    </div>
</template>

<style scoped>
    .comp {
        border: 1px blue dashed;
        padding: 1rem;
    }
</style>