<template>
    <h4>{{name}}</h4>
</template>

<script>
    export default {
        name: 'Footer',
        data()
        {
            return{
                name: "Kristiyan © All rights reserved Copyrights 2022"
            }
        }
    }
</script>

<style lang="scss" scoped>

h4 {
    margin-top: 50px;
    padding: 30px;
    background: #42b983;
    color: white;
}
</style>