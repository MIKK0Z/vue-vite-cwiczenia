<script>
    import Json from "./data/cars_full.json";
    import MyCar from "./components/MyCar.vue";

    export default {
        data() {
            return {
                title: "03: show more cars",
                idCap: 10,
            }
        },
        components: {
            MyCar,
        },
        methods: {
            showMoreCars() {
                this.idCap += 10;
            }
        },
        computed: {
            filteredCars() {
                return Json.filter(car => car.id <= this.idCap);
            },
        }
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <template v-for="car in filteredCars" :id="car.id">
            <MyCar :car="car"/>
        </template>

        <button @click="showMoreCars">
            show more cars
        </button>
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: .5rem;
        margin-block: 1rem;
    }

    button {
        display: block;
    }
</style>
