<script>
export default {
    data(list) {
        return {
            list: ['foo', 'bar']
        }
    }
}

</script>
<template>

    <div v-for="ele in list">
        {{ ele }}</div>

</template>