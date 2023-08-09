<template>
<h1>Child Component</h1><br>
<div>

    <h3>{{ hello }} <br>
        name : {{ name }} <br>
        Objects : {{ data }}</h3>

</div>
</template>

<script>
export default {
    name: 'ChildofHome',
    props: {
        hello: String,
        name: String,
        data: Object

    }
}
</script>

<style scoped>
h1 {
    color: blue;
}

h3 {
    color: brown;
}
</style>
