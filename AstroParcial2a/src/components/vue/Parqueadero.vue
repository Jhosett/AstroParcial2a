<script setup>

import { ref } from 'vue'

const arrayMotos = ref([true,true,false,true,true,false,true,true,true]);
const arrayCarros = ref([true,true,true,false,true,true,false,true,true,true,true,true]);
const counter = ref(0)

function changeColor(index, array, precio) {

    if (!array[index]) {
        counter.value += precio
    }

    array[index] = !array[index]

}

</script>

<template>

    {{ counter }}

   <div class="p-10 flex justify-center gap-10">

        <section class="grid grid-cols-3 gap-4 w-[400px]">
            <div @click="changeColor(index, arrayMotos, 500)" v-for="(array, index) in arrayMotos" class="w-full h-28" 
            :class="{'bg-green-500':array}, {'bg-red-500':!array}">
            </div>
        </section>

        <section class="grid grid-cols-4 gap-4 w-[600px]">
            <div @click="changeColor(index, arrayCarros, 1000)" v-for="(array, index) in arrayCarros" class="w-full h-28" 
            :class="{'bg-green-500':array}, {'bg-red-500':!array}">
            </div>
        </section>

   </div>

</template>