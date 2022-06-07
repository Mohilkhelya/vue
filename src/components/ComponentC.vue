<template>
    <div>
        <h2>ComponentC</h2>
        <h2>Component F user name :- {{username}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'ComponentC',

        inject:[ 'username' ]
    }
</script>

<style lang="scss" scoped>

</style>