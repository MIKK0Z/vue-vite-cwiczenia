<script>
    import MyBtn from "./components/MyBtn.vue";
    import BtnWithData from "./components/BtnWithData.vue";
    import BtnWithProps from "./components/BtnWithProps.vue";
    import SelectWithData from "./components/SelectWithData.vue";
    import SelectWithProps from "./components/SelectWithProps.vue";

    export default {
        data() {
            return {
                title: "00: vue + vite",
                elements: ["1", "2", "3"],
            }
        },
        components: {
            MyBtn,
            BtnWithData,
            BtnWithProps,
            SelectWithData,
            SelectWithProps,
        }
    }
</script>

<template>
    <h1>{{ title }}</h1>

    <div class="wrapper">
        <MyBtn />
        <MyBtn />
        <MyBtn />
    </div>

    <div class="wrapper">
        <BtnWithData />
        <BtnWithProps bgColor="red" msg="btn with passed data" />
    </div>

    <div class="wrapper">
        <SelectWithData />
        <SelectWithProps :elements="elements" />
    </div>
</template>

<style scoped>
    .wrapper {
        border: 1px red dashed;
        padding: 1rem;
        margin-block: 1rem;

        & > * + * {
            margin-top: 1rem;
        }
    }
</style>
