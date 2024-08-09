<template>
   <h2 class="font-bold text-2xl text-gray-700 uppercase">{{ title }}</h2>
  <div class="flex flex-col items-end">
    <h4 class="mt-5 uppercase font-bold"> {{subTitle}}</h4>
   <h1 id="balance" class="font-bold text-4xl text-blue-700">€{{solde}}</h1>
  </div>
 
</template>

<script setup>
defineProps({
    title:String, 
    subTitle:String,
    solde:Number
})
</script>