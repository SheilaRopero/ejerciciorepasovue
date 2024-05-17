<script setup>
import { ref } from 'vue';
const arreglo = ref(['Tema 1','Tema 2','Tema 3'])
const text = ref (['','',''])
const mostrar = ref(null)

function mostrartexto(index){
    mostrar.value = index;

    console.log('hola')
}

function mostrarholder(index){
    return 'Tema del texto: ' + (index+1)
}

</script>

<template>
    <div class="mx-auto w-96 border-2 px-6 py-4 shadow bg-blue-300 mt-10">
        <div  class="flex flex-col space-y-2 ">
            <div class="relative" v-for="(arreglos,index) in arreglo" :key="index">
                <div>
                    <li class="list-none bg-blue-200 flex justify-between px-4 py-2">{{ arreglos }}
                <button @click="mostrartexto(index)" >+</button>
            </li>
                </div>
                <div v-if="mostrar===index" class="bg-blue-200 p-2 mt-2 w-full">
            <input class="bg-white w-full h-20 p-2" v-model="text[index]" type="text"    :placeholder="mostrarholder(index)">

           </div>

            
            </div>
           
        </div>
    </div>
    

   
</template>