<template>
    <div class = 'center'>
        <div class = 'calculator'>  
            <div class = 'display' style = 'border-radius: 10px 10px 0 0'><div class = 'circle' style = 'background-color: red'></div><div class = 'circle' style = 'background-color: yellow'></div><div class = 'circle'></div>
            <div class = 'now'>
            {{now || 0}}
            </div>
            </div>
            <div v-on:click="clear" class = 'button'>AC</div>    
            <div class = 'button'>+/-</div>    
            <div class = 'button'>%</div>    
            <div class = 'button orange'>÷</div>    
            <div v-on:click="number('7')" class = 'button'>7</div>    
            <div v-on:click="number('8')" class = 'button'>8</div>    
            <div v-on:click="number('9')" class = 'button'>9</div>    
            <div v-on:click="multiply" class = 'button orange'>*</div>    
            <div v-on:click="number('4')" class = 'button'>4</div>    
            <div v-on:click="number(5)" class = 'button'>5</div>    
            <div v-on:click="number('6')" class = 'button'>6</div>    
            <div v-on:click="minus" class = 'button orange'>-</div>    
            <div v-on:click="number('1')" class = 'button'>1</div>    
            <div v-on:click="number('2')" class = 'button'>2</div>    
            <div v-on:click="number('3')" class = 'button'>3</div>    
            <div v-on:click="add" class = 'button orange'>+</div>    
            <div v-on:click="zero" class = 'button zero'>0</div>    
            <div v-on:click="dot" class = 'button'>.</div>    
            <div v-on:click="equal" class = 'button orange' style = 'border-radius: 0 0 10px'>=</div>    
        </div>
    </div>
</template>

<script>
    export default{
        
        data() {
            return {
                now: '',
                hold: null,
                operator: null,
                opClicked: false
            }
        },
        methods: {
            clear () {
                this.now = '';
            },
            number(num) {
                this.now = `${this.now}${num}`;
            },
            zero () {
                if(this.now != 0){
                    this.now = this.now + 0;
                } 
            },
            dot() {
                if(this.now.indexOf('.') === -1) {
                    this.number('.');
                }
            },
            percent() {
                
            },
            add() {
                // this.hold = this.now;
                // this.now = '';
                // console.log(this.hold)
                this.operator = (a, b) => a + b;
                this.hold = this.now;
                this.now = '';
                this.opClicked = true;
            }, 
            minus() {
                this.operator = (a, b) => b - a;
                this.hold = this.now;
                this.now = '';
                this.opClicked = true;
            },
            multiply() {
                this.operator = (a, b) => a * b;
                this.hold = this.now;
                this.now = '';
                this.opClicked = true;
            },
            equal() {
                this.now = `${this.operator(+this.now , +this.hold)}`
                console.log(this.now)
                this.hold = null;
            }
        }
    } 
</script>

<style >
    .now {
       color: white;
       float: right;

    }

    .center {
        padding-top: 15%;
    }

    .circle {
        height: 15px;
        width: 15px;
        margin-left: 8px; 
        margin-top: 4px;
        border-radius: 50%;
        background-color: green;
        float: left;
    }

    .calculator {
       display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: minmax(50px, auto);
        background-color: lightgrey;
        width: 260px;
        height: 350px;
        margin:  auto;
        border-radius: 10px;
        top: 50%;
    }

    .display { 
        grid-column: 1/5;
        background-color: lightblue;
        font-size: 30px;
        padding-right: 40px;
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