<script setup>

    import { ref } from "vue"

    let number = ref(5)
    let text = ref("")

    function add(){
        number.value++
        console.log(number.value)
    }

    function less(){
        if(number.value > 0){
            number.value--
        }
        console.log(number.value)
    }
</script>

<template>
    <div class="max-w-96 bg-gray-500 items-center rounded py-3 px-5 mx-auto flex flex-col">
        
        <div 
            class="bg-black px-2 flex items-center justify-center rounded text-white" 
            v-if="number > 0"
        >
           Seguidores: {{ number }}
        </div>
        <div
        v-else
        >
        No hay ninguno papu :'v
        </div>

        <div class="w-full flex flex-row justify-between px-5">
            <div class="bg-black size-8 flex items-center justify-center rounded text-red-500 cursor-pointer" @click="less()">
                -
            </div>
            <div 
                class="bg-black size-8 flex items-center justify-center rounded text-green-500 cursor-pointer"
                @click="add()"
            >
                +
            </div>
        </div>
    </div>
</template>