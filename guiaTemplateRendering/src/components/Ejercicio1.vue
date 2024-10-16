// Actividad guiada: une mejor experiencia de usuario/a

<script>
    export default {
        name: 'Ejercicio1',
        data () {
            return {
                fondo: "",
                colores: ["green", "purple", "pink", "black"],
                espaciado: "",
                elegirColor: "",
                horario:"",

        }
        }
    }
</script>

<template>
    <h2>Ej1: una mejor UX</h2>

    <div>
    <select v-model="fondo">
        <option v-for="color in colores">{{ color }}</option>
    </select>
    <h1 
        :style="{ background: fondo }"
        :class="{ 'text-white': fondo == 'black'}">
        Este txt cambiará de color (estilos enlazados)
    </h1>
    </div>
    <hr>
    <div>
        <h2>Ej2: selector de separación de caracteres</h2>
        <input type="range" v-model="espaciado">
        <h3 :style="{ 'letterSpacing': espaciado + 'px' }">Este texto se irá separando</h3> 
        <!-- El selector solo arroja un rango, de 0 a 100, pero puede ser cualquier valor, así que le agregamos la unidad 'px' -->
    </div>
    <hr>
    <div>
        <h2>Ej3: selector de color</h2>
        <input type="color" v-model="elegirColor">
        <div :style="{ backgroundColor: elegirColor, height: '100px', width: '200px', border: 'solid 1px black', paddingBottom: '1rem' }"></div>
    </div>
    <hr>
    <div>
        <h2>Ej4: selector de tiempo</h2>
        <input type="time" v-model="horario">
        <div style="height: 100px; width: 200px; border: solid 1px black;"  :class="{'mañana': horario >= '00:00:00' && horario < '12:00:00', 'tarde': horario >= '12:00:00' && horario < '19:00:00', 'noche': horario >= '19:00:00'}">
                    <span>{{ horario >= '00:00:00' && horario < '12:00:00' ? 'Mañana' : (horario >= '12:00:00' && horario < '19:00:00' ? 'Tarde' : 'Noche') }}</span>
        </div>
    </div>
</template>

<style scoped>
    .text-white {
    color: white;
    }

    .mañana {
        background-color: rgb(243, 243, 167);
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2rem;
        font-weight: bold;
    } 
    .tarde {
        background-color: orange;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2rem;
        font-weight: bold;
    }
    .noche {
        background-color: darkblue;
        color: aliceblue;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2rem;
        font-weight: bold;
    }

</style>