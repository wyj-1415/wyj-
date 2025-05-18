<template>
    <div id="app">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
        <router-view></router-view>
    </div>
</template>

<script>
export default {
    name: 'App'
}
</script>

<style>
#app {

    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>