<script >
import { RouterLink, RouterView } from 'vue-router'




let c1 = 0
let c2 = 0
let c3 = 0
let c4 = 0
let c5 = 0
let c6 = 0

let comuna1 = [
  '20 de julio',
  'el llano',
  'las cajas',
  'santa ana',
  'san jose',
  'urbanizacion central',
  'hacaritama',
  'tacaloa',
  'san agustin',
  'la modelo'
]
let comuna2 = [
  'El Dorado',
  'Nuevo Horizonte',
  'Cañaveral',
  'El Carmen',
  'Simón Bolívar',
  'Sesquicentenario',
  'Fundadores',
  'Comuneros',
  'Urbanización Los Alpes',
  'El Retiro',
  'El Peñón',
  'Urbanización Bruselas',
  'Cristo Rey',
  'Betania',
  'Nueve de Octubre',
  'Palomar'
]
let comuna3 = [
  'Camino Real',
  'Santa Lucia',
  'La Piñuela-San Antonio',
  'Gustavo Alayon',
  'La Palmita',
  'Las Mercedes',
  'El Carretero',
  'La Costa',
  'La Favorita',
  'Villa Nueva',
  'La Quinta',
  'San Fermín',
  'El Llanito',
  'La Esperanza',
  'Doce de Octubre',
  'El Bosque',
  'Los Almendros',
  'El Bambo',
  '26 de Julio',
  'Carbón-Ramal',
  'Cuesta Blanca',
  'Promesa de Dios',
  'Nueva Madrid',
  'La Paz',
  'Belén',
  'Quebrada El Tejar',
  'Las Alcantarillas',
  'Olaya Herrera',
  'Jorge Eliécer Gaitán'
]
let comuna4 = [
  'Santa Cruz',
  'El Tejarito',
  'Junín',
  'La Torcoroma',
  'Juan XXIII',
  'La Libertad',
  'El Landia',
  'La Esmeralda',
  'Marabelito',
  'Marabel',
  'Nueva España',
  'IV Centenario',
  'Camilo Torres',
  'San Rafael',
  'Primero de Mayo',
  'Las delicias',
  'Asentamiento Humano Villa Rosa',
  '15 de Agosto',
  'Las Villas',
  'Bella Vista',
  'Urbanización Albania',
  'Urbanización Villa Carolina'
]
let comuna5 = [
  'Las Ferias',
  'Buenos Aires',
  'Las Palmeras',
  'La Primavera',
  'Ciudad Jardín',
  'El Lago',
  'Los Acacios',
  'Avenida Francisco Fernández de Contreras',
  'Altos de la Colina',
  'Villas de Antón',
  'Jardines de la Rosa',
  'Altos de la Primavera',
  'Prados del Lago',
  'Miradores del Lago',
  'Miradores del Caracolí'
]
let comuna6 = [
  'Santa Clara',
  'Bermejal',
  'Urbanización Colinas de La Florida',
  'El Líbano',
  'La Gloria',
  'Dos de Octubre',
  'Villa Paraíso',
  'La Perla',
  'Altos del Norte'
]

// Función para crear conjuntos de los barrios por comuna
function crearSet(array) {
  let set = new Set()
  array.forEach((elemento) => {
    set.add(elemento.toLowerCase()) // Convertir a minúsculas para hacer la comparación insensible a mayúsculas
  })
  return set
}

// Crear conjuntos de los barrios por comuna
let comunaSet1 = crearSet(comuna1)
let comunaSet2 = crearSet(comuna2)
let comunaSet3 = crearSet(comuna3)
let comunaSet4 = crearSet(comuna4)
let comunaSet5 = crearSet(comuna5)
let comunaSet6 = crearSet(comuna6)

export default {
  data() {
    return {
      newItem: {
        name: '',
        lastName: '',
        documento: '',
        barrio: ''
      },
      items: []
    }
  },
  methods: {
    addItem() {
      this.items.push({
        name: this.newItem.name,
        lastName: this.newItem.lastName,
        documento: this.newItem.documento,
        barrio: this.newItem.barrio
      })

      // Verificar a qué comuna pertenece el barrio
      if (comunaSet2.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 2.')
        c2++
      } else if (comunaSet3.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 3.')
        c3++
        console.log(c3)
      } else if (comunaSet4.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 4.')
        c4++
      } else if (comunaSet5.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 5.')
        c5++
      } else if (comunaSet6.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 6.')
        c6++
      } else if (comunaSet1.has(this.newItem.barrio)) {
        console.log(this.newItem.barrio + ' pertenece a la comuna 1.')
        c1++
      } else {
        console.log(this.newItem.barrio + ' no pertenece a ninguna comuna conocida.')
      }

      // Limpiar los campos de entrada
      this.newItem.name = ''
      this.newItem.lastName = ''
      this.newItem.documento = ''
      this.newItem.barrio = ''
    }
  }
}

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
        <RouterLink to="/about">About</RouterLink>

      </li>
    </ul>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
