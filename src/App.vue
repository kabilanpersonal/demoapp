<template>
<img alt="Vue logo" src="./assets/logo.png">
<HelloWorld msg="Welcome to Your Vue.js App" />
<HomeMain />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HomeMain from './components/HomeMain.vue';

export default {
    name: 'App',
    components: {
        HelloWorld,
        HomeMain
    }
}
</script>


