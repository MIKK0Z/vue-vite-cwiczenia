<script>
    import Json from "./data/cars_full.json";
    import MyCarBuy from "./components/MyCarBuy.vue";
    import MyCarBought from "./components/MyCarBought.vue";

    export default {
        data() {
            return {
                title: "05: buy car",
                year: 2003,
                boughtCars: [],
                availabeYears: [],
            }
        },
        components: {
            MyCarBuy,
            MyCarBought,
        },
        computed: {
            filteredCars() {
                return Json.filter((car) => car.car_year === this.year);
            }
        },
        watch: {
            year(newVal) {
                this.year = parseInt(newVal)
            }
        },
        methods: {
            buyCar(id) {
                this.boughtCars = [...this.boughtCars, Json.find((car) => car.id === id)];
            },
            removeCar(id) {
                this.boughtCars = this.boughtCars.filter((car) => car.id !== id);
            },
        },
        mounted() {
            this.availabeYears = [...new Set(Json.map((car) => car.car_year))];
        }
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <select v-model="year">
            <option v-for="year in availabeYears" :value="year">
                {{ year }}
            </option>
        </select>

        <main>
            <div>
                <h2>availabe cars</h2>
                <template v-for="car in filteredCars" :id="car.id">
                    <my-car-buy :car="car" :buy="buyCar" />
                </template>
            </div>
            
            <div>
                <h2>bought cars</h2>
                <template v-for="car in boughtCars">
                    <my-car-bought :car="car" :remove="removeCar" />
                </template>
            </div>
        </main>
        
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: .5rem;
        margin-block: 1rem;
    }

    main {
        display: flex;
        justify-content: space-between;

        & > div {
            flex: 1;
        }
    }
</style>
