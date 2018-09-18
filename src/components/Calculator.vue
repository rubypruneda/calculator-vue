<template>
    <div>
        <p>
            is it working?
        </p>
        <div class = 'calculator'>  
            <div class = 'display-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
            <div class = 'little-box'></div>    
        </div>
    </div>
</template>

<script>
    
</script>

<style >
    .calculator {
        height: 450px;
        width: 330px;
        background-color: skyblue;
        margin: auto;
        padding-top: 10px;
    }

    .little-box {
        height: 62px;
        width: 62px;
        display: grid;
        background-color: pink;
        margin: 10px;
         grid-row: auto / auto;
         float: left;
    }

    .display-box {
        height: 60px;
        width: 90%;
        background-color: yellow;
        margin: auto;
        margin-bottom: 20px;
    }
</style>