<script>
export default {
    props:['title'],

    data() {
        return {
            counter: 0,
            fullName: {
                firstName: '',
                lastName: ''
            }
        }
    },

    // called when component created for the 1st time
    created() {
        console.log('creaTED called');

    },

    // called when component mounted for the 1st time
    mounted() {
        console.log('mounted called');

        console.log(this.counter)
    },

    // called before component unmounted
    unmounted() {
        console.log('unmounted called');
    },

    // returns computed properties
    computed: {
        getCounter() {
            return this.counter
        },

        fullName: {
            get() {
                return this.firstName + this.lastName
            },
            set(value) {
                [this.firstName, this.lastName] = value?.split(" ")
            }
        }
    },

    // all helper methods required 
    methods: {
        increment(e) {
            this.counter++
        },
        decrement() {
            console.log('decrement called');

            this.counter--
        },
        setFullName(e) {

            this.fullName=e.target.value
        }
    }
}

</script>

<template>
    <div>
        <header>{{title}}</header>
        <div>Welcome Mr. {{ fullName.get }}</div>

        <div>
            Counter: {{ getCounter }}
            <button id="app" @click="increment">Increment</button>
            <button @click="decrement">Decrement</button>
        </div>
        <input @change="setFullName"/>
    </div>
</template>
<style>
</style>