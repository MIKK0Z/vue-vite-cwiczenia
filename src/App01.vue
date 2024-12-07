<script>
    import Json from "./data/cars.json";

    export default {
        data() {
            return {
                title: "01: cars without components",
                cars: Json,
            }
        },
        methods: {
            getStateColor(damaged) {
                return damaged ? "red" : "lime";
            },
        },
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <template v-for="car in cars" :id="car.id">
            <div class="car">
                <div :style="{ backgroundColor: car.hex_color }">
                    kolor auta
                </div>
                <div :style="{ backgroundColor: getStateColor(car.damaged) }">
                    {{ car.damaged ? "uszkodzony" : "sprawny" }}
                </div>
                <img :src="car.image" :alt="car.car_name">
                <p>id: {{ car.id }}</p>
                <p>name: {{ car.car_name }}</p>
            </div>
        </template>
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: 1rem;
        margin-block: 1rem;
    }

    .car {
        display: inline-block;

        & > div {
            padding: 0.5rem;
            text-align: center;
        }

        & + * {
            margin-left: 1rem;
        }
    }
</style>
