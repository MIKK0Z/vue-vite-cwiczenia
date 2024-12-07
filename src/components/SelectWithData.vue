<script>
    export default {
        data() {
            return {
                elements: ["a", "b", "c"],
            }
        }
    }
</script>

<template>
    <div class="comp">
        data in comp
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