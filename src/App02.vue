<script>
    import Json from "./data/cars.json";
    import MyCar from "./components/MyCar.vue";

    export default {
        data() {
            return {
                title: "02: cars with components",
                cars: Json,
            }
        },
        components: {
            MyCar,
        },
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <template v-for="car in cars" :id="car.id">
            <MyCar :car="car"/>
        </template>
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: 1rem;
        margin-block: 1rem;
    }
</style>
