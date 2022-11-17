<template>
    <div class="container">
        <div class="box">
            <div class="titulo">
                <h2>CALCULATOR</h2>
            </div>
            <div class="columns">

                <div class="col-80">
                    <div class="row">
                        <label> VALUE 1:
                            <input type="number" v-model="value1" />
                        </label>
                    </div>
                    <div class="row">
                        <label> VALUE 2:
                            <input type="number" v-model="value2" />
                        </label>
                    </div>
                    <div class="row">
                        <label> RESULT:
                            <input type="number" v-model="result" />
                        </label>
                    </div>
                </div>

                <div class="col-20">
                    <div class="row">
                        <button style="color: blue;" v-on:click="adicao">
                            SOMAR
                        </button>
                    </div>
                    <div class="row">
                        <button style="color: blue;" v-on:click="subtracao">
                            SUBTRAIR
                        </button>
                    </div>
                    <div class="row">
                        <button style="color: blue;" v-on:click="multiplicacao">
                            MULTIPLICAR
                        </button>
                    </div>
                    <div class="row">
                        <button style="color: blue;" v-on:click="divisao">
                            DIVIDIR
                        </button>
                    </div>
                    <div class="row">
                        <button style="color: red;" v-on:click="clear">
                            LIMPAR
                        </button>
                    </div> 
                </div>

            </div>
        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'CalculatorBlock',
    data () {
        return {
            value1: null,
            value2: null,
            result: null,
        }
    },
    methods: {
        adicao () {
            if(this.validation()){
                this.result = this.value1 + this.value2;
            }
        },
        subtracao () {
            if(this.validation()){
                this.result = this.value1 - this.value2;
            }
        },
        multiplicacao () {
            if(this.validation()){
                this.result = this.value1 * this.value2;
            }
        },
        divisao () {
            if(this.validation()){
                this.result = this.value1 / this.value2;
            }
        },
        clear () {
            this.value1 = null;
            this.value2 = null;
            this.result = null;
        },
        validation () {
            if(this.value1 == null || this.value2 == null){
                alert('Complete os campos: (Obrigatório)');
                return false;
            }
            return true;
        }
    }
})
</script>

<style>
input {
  display: block;
  height: 25px;
  border-radius: 2px;
  border-color: darkgray;
  width: 100%;
}
h2 {
    margin-left: 30px;
    color: white;
}
button {
    min-height: 30px;
    min-width: 100px;
    border-color: darkgray;
    border-style: solid;
    border-radius: 5px;
}
.box {
    width: 500px;
    height: 350px;
    background: #fff;
    border-color: darkgray;
    border-style: solid;
    border-radius: 10px;
}
.titulo {
    background: gray;
    margin: 5px;
    border-color: darkgray;
    border-style: solid;
    border-radius: 10px;
}
.container{
    width: 100vw;
    height: 100vh;
    background: #6C7A89;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center
}

.columns {    
    margin: 5px;
    display: flex;
    flex-direction: row;
    flex-flow: row wrap;
    align-items: center;
}

.col-80 {
    width: 70%;
    height: 250px;
    text-align: left;
}
.col-20 {
    width: 30%;
    height: 250px;
    text-align: center;
}
.row{
    min-height: 30px;
    margin-top: 20px;

}
</style>