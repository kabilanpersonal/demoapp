<template>
    
    <div>
    <p>Passing data from Child to Parent....</p>
    <button type="button" v-on:click="result(Childname)">Get Child Name</button>
        
    </div>
    </template>
    
    <script>
    export default {
        name: 'ChildtoParent',
        props: {
            result : Function 
    
        },
        data() {
            return {
                  Childname : "Chitti",
            }
        }
    }
    </script>
    
    <style scoped>
    h1 {
        color: blue;
    }
    
    h3,p {
        color: crimson;
    }
    </style>
    