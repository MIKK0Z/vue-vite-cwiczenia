<script>
    import Json from "./data/cars_full.json";
    import MyCar from "./components/MyCar.vue";

    export default {
        data() {
            return {
                title: "04: year filter",
                year: 2003,
            }
        },
        components: {
            MyCar,
        },
        computed: {
            filteredCars() {
                return Json.filter(car => car.car_year === this.year);
            },
        },
        watch: {
            year(newYear) {
                console.log("Year changed to:", newYear); // Debug to see if changes are detected
            }
        }
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <input type="range" min="1900" max="2100" v-model="year">

        {{ year }}

        <br>

        <template v-for="car in filteredCars" :id="car.id">
            <MyCar :car="car"/>
        </template>
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: .5rem;
        margin-block: 1rem;
    }
</style>
