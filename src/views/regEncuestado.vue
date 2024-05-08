<script setup></script>

<template class="bg-black">
  <div>
    <form @submit.prevent="addItem">
      <input v-model="newItem.name" placeholder="nombre" class="text-red-950" />
      <input v-model="newItem.lastName" class="text-red-950" placeholder="apellido" />
      <input v-model="newItem.documento" class="text-red-950" placeholder="documento" />
      <input v-model="newItem.barrio" class="text-red-950" placeholder="barrio" />
      <button type="submit">Add</button>
    </form>
  </div>
</template>
