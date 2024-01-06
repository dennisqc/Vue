import type { DefineComponent from 'vue';
<template>
    <h2>Counter</h2>

    <p>{{ counter }} <sup>2</sup> = {{ SquaredCounter }}</p>
    <div>
        <button @click="increment">+1</button>
        <button @click="decrement">-1</button>
    </div>
</template>

<script>
export default {
    props: {
        start: {
            type: Number,
            default: 1
        }
    },
    data() {
        return {
            counter: this.start,
        };
    },
    methods: {
        getSquaredValue() {
            console.log("getSquaredValue");
            return (this.counter = this.counter);
        },
        increment() {
            return this.counter++
        },
        decrement() {
            console.log(this.counter <= 1);
            if (this.counter > 1) {
                return this.counter--
            }

        }
    },
    computed: {
        SquaredCounter() {
            console.log("SquaredCounter");
            return this.counter = this.counter;
        },
    },
};
</script>

<style></style>
