<template>
    <h1>Esto es VUE.js</h1>
    <h1>{{ titulo }}</h1>
    <h2>{{ subtitulo }}</h2>
    <h1>{{ contador }}</h1>
    <input type="text" v-model="titulo">
    <input type="text" v-model="subtitulo">
    <input type="text" v-model="contador">
    <button @click="contador++">+</button>
    <button @click="decrementar()">-</button>
    <button @click="cambiarTitulo('Hola este es mi mensaje')">Cambiar titulo</button>
    <button @click="consumirDatos()">Consumir Datos</button>
</template>

<script>
import axios from "axios"

export default {
        data(){
            return {
                titulo: "Aprendiendo Vue.js",
                subtitulo: "Vue CDN",
                contador: 1
            }
        },
        methods: {
            incrementar(){
                this.contador++;
            },
            decrementar(){
                this.contador--;
            },
            cambiarTitulo(mensaje){
                this.titulo = mensaje
            },
            consumirDatos(){
                fetch('https://jsonplaceholder.typicode.com/todos')
                    .then(response => response.json())
                    .then(json => console.log(json))
            }
        }
    }
</script>