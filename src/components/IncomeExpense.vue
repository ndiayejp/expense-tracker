<template>
<div class="bg-white px-2.5 py-1.5 mt-5 flex justify-between">
    <div class="flex flex-col items-center gap-2">
        <h4 class="uppercase">{{ title1 }}</h4>
        <p id="money-plus" class="money plus font-bold text-2xl text-green-600"> {{income}}€</p>
    </div>
    <div class="flex flex-col items-center gap-2">
        <h4 class="uppercase">{{title2}}</h4>
        <p id="money-minus" class="money minus font-bold text-2xl text-red-600">{{expenses}}€</p>
    </div>
</div>
</template>

<script setup>
    defineProps({
        title1:String, 
        title2:String, 
        income: Number, 
        expenses: Number

    })
</script>