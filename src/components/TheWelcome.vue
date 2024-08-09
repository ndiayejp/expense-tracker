
<template>
   <Header :title="'Suivi des dépenses'" :subTitle="'Balance'" :solde="0.00"/>
  <div class="inc-exp-container">
    <IncomeExpense :title1="'Revenue'" :title2="'Dépenses'" :income="+2000" :expenses="-600"/>
    <TransactionsList :title="'Historique'" :transactions="transactions"/>
    <AddTransaction :title="'Ajouter une nouvelle transaction'" :categories="categories" @saveTransaction="saveForm"/>
  </div>

</template>

<script setup>
import { ref } from 'vue';
import 'boxicons'
import Header from "@/components/Header.vue"
import TransactionsList from "@/components/TransactionsList.vue"
import IncomeExpense from "@/components/IncomeExpense.vue"
import AddTransaction from "@/components/AddTransaction.vue"
 const categories = [
  {
    id  : 1,
    name  : "Food & Dining" ,
    slug  : ""
  },
  {
    id    : 2,
    name  : "Transport" , 
    slug  : "transport"
  },
  {
    id    : 3,
    name  : "Utilitaire", 
    name  : "utilitaire"
  },
  {
    id    : 4,
    name  : "Entertainment", 
    slug  : "entertainment"
  },
  {
    id    : 5,
    name  : "Santé" , 
    slug  : "sante"
  },
  {
    id    : 6,
    name  : "Vêtements" , 
    slug  : "vetements"
  },
  {
    id    : 7,
    name  : "Voyages" , 
    slug  : "voyages"
  }, 
  {
    id    : 8,
    name  : "Beauté" , 
    slug  : "beauté"
  }, 
  {
    id    : 9,
    name  : "Factures" , 
    slug  : "factures"
  }, 
  {
    id    : 10,
    name  : "Loisirs" , 
    slug  : "loisirs"
  }, 
  {
    id    : 11,
    name  : "Cadeaux" , 
    slug  : "cadeaux"
  }, 
  {
    id    : 12,
    name  : "Nourritures" , 
    slug  : "nourritures"
  }, 
  {
    id    : 13,
    name  : "Voiture" , 
    slug  : "voiture"
  }
]
const formData = ref({
  text:"", 
  amount:"", 
  category:"", 
  date:Date.now()
})
const transactions = ref([
  { id: 1, text: 'Flower', amount: -20, category: 2, date:Date.now() },
])
const saveForm = (e)=>{
  console.log(e.amout.value)
  //transactions.value.push(formData.value)
}
</script>
