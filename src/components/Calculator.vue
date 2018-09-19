<template>
    <div>
        <p>
            is it working?
        </p>
        <div class = 'calculator'>  
            <div class = 'display' style = 'border-radius: 10px 10px'>{{now || 0}}</div>
            <div v-on:click="clear" class = 'button'>AC</div>    
            <div class = 'button'>+/-</div>    
            <div class = 'button'>%</div>    
            <div class = 'button orange'>÷</div>    
            <div class = 'button'>7</div>    
            <div class = 'button'>8</div>    
            <div class = 'button'>9</div>    
            <div class = 'button orange'>*</div>    
            <div class = 'button'>4</div>    
            <div class = 'button'>5</div>    
            <div class = 'button'>6</div>    
            <div class = 'button orange'>-</div>    
            <div class = 'button'>1</div>    
            <div class = 'button'>2</div>    
            <div class = 'button'>3</div>    
            <div class = 'button orange'>+</div>    
            <div class = 'button zero'>0</div>    
            <div class = 'button'>.</div>    
            <div class = 'button orange' style = 'border-radius: 0 0 10px'>=</div>    
        </div>
    </div>
</template>

<script>
    export default{
        data() {
            return {
                now: ';lkj',
            }
        },
        methods: {
            clear () {
                this.now = '';
            }
        }
    }
</script>

<style >
    .calculator {
       display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: minmax(50px, auto);
        background-color: lightgrey;
        width: 260px;
        height: 350px;
        margin: auto;
        border-radius: 10px;
    }

    .display { 
        grid-column: 1/5;
        background-color: lightblue;
    }

    .zero {
        grid-column: 1/3;
        border-radius: 0 0 0 10px;
    }

    .button {
        padding-top: 13px;
        border: 1px solid grey; 
        font-size: 23px;
        font-weight: 500;
    }

    .orange { 
        background-color: orange;
        color: white;
        font-size: 35px;
        font-weight: 200;
    }

</style>