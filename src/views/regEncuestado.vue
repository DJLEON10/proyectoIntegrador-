<script setup>
import {ref} from 'vue'
import { useName } from '@/composable/data'

//const { name } = useName()

//const a = ref(0)
</script>



<template>
  <div>
    <form @submit.prevent="addItem">
      <input v-model="newItem.name" placeholder="nombre" class="text-red-950" />
      <input v-model="newItem.lastName" class="text-red-950" placeholder="apellido" />
      <input v-model="newItem.documento" class="text-red-950" placeholder="documento" />
      <input v-model="newItem.barrio" class="text-red-950" placeholder="barrio" />
      <button type="submit">Add</button>
    </form>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item.name }} {{ item.lastName }} {{ item.documento }} {{ item.barrio }}
        <a href="#">encuesta1</a>
      </li>
    </ul>
  </div>
</template>
    soy una nueva vista {{ a }}
    {{ name }}
