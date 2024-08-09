<template> 
    <h3 class="my-3 border-b font-bold text-lg text-gray-600">{{ title }}</h3>
    <form id="form" @submit.prevent="addTransaction">
      <div class="mb-2">
        <label class="block mb-2 text-sm font-medium text-gray-900">Libellé</label>
        <input v-model="text" class="border border-gray-300 text-gray-900 text-sm rounded-0 focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5" type="text" id="text" placeholder="Enter text..." />
      </div>
      <div class="mb-2">
        <label class="block mb-2 text-sm font-medium text-gray-900">Montant <br /><span class="text-xs text-gray-400"> (negative - expense, positive - income)</span></label>
        <input v-model="amount" class="border border-gray-300 text-gray-900 text-sm rounded-0 focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5" type="number" id="amount" placeholder="Montant..." />
      </div>
      <div class="mb-2">
        <label class="block mb-2 text-sm font-medium text-gray-900" for="category">Catégorie</label>
        <select v-model="category" class="border px-2 p-2.5 w-full rounded-0">
          <option value="">Choisissez une catégorie</option>
          <option v-for="category in categories" :key="category.id" :value="category.id">{{ category.name }}</option>
        </select>
      </div>
      <button type="submit" class="text-white w-full mt-2 bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-0 text-sm  px-5 py-2.5 text-center ">Enregistrer</button>
    </form>
</template>

<script setup>
 defineProps({
    title:String,
    categories:Object
  })
  const text = defineModel("text");
  const amount = defineModel("amount");
  const category = defineModel("category");

  const emits  = defineEmits('saveTransaction')

  const addTransaction = ()=>{
    emits('saveTransaction',{text:text,amout:amount, category:category, date:Date.now()})
  }
</script>