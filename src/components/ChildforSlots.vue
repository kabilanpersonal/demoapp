<template>
    
    <div>
        <slot></slot>
    </div>
    </template>
    
    <script>
    export default {
        name: 'ChildforSlots',
        
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