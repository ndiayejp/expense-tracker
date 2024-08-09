<template>
<h3 class="my-3 border-b font-bold text-lg text-gray-700">{{title}}</h3>
    <ul class="list">
      <li v-for="transaction in transactions" :key="transaction.id" class="relative bg-white mb-2 shadow-md px-3.5 py-1.5 flex justify-between items-center">
        {{transaction.text}} <span>{{transaction.amount}}€</span>
        <span class="absolute w-1 h-full bg-red-600 right-0"></span>
        <button class="absolute -left-6 top-0 px-1.5 py-.5 bg-red-600 hover:bg-red-500 text-white">
          <box-icon name="trash" color="white" size="xs"></box-icon>
        </button>
      </li>
       
    </ul>
</template>

<script setup>
defineProps({
    title:String,
    transactions:Object
})
</script>