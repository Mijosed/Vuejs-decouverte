<script setup>
import Navbar from './components/Navbar.vue';
import HelloWorld from '@/components/HelloWorld.vue';
import { ref, reactive, computed, watch } from 'vue';

// const user = reactive({
//   name: 'Mijosé',
//   age: 18
// });

const name = ref('Mijosé')
const age = ref(19)
const sentence = computed(() => {
    return `Bonjour, je m'appelle ${name.value} et j'ai ${age.value}`
});
watch(name, (oldValue, newValue) => {
  console.log(oldValue, newValue);
});

const nombre = ref(2);

// const display = () => {
//   console.log(user.name, user.age);
// };

const count = () => {
  nombre.value = nombre.value + 1;
  console.log(nombre.value);
}

// display();

</script>

<template>

<!-- <div 
class="bold"

:class="[ user.age > 20 ? 'text-red' : 'text-green' ]">
  <HelloWorld>
    <template v-slot:name> 
      {{ user.name }}
    </template>
    <template v-slot:age>
      {{ user.age }}

    </template>
  </HelloWorld>
</div> -->

  <!-- <input type="text" v-model="user.name" @input="display" ></input>
<input type="text" v-model="user.age" ></input> -->
  <Navbar/>
  <button v-on:click="count">Test</button>
  <br>
  <div>
  <span> {{ sentence }}</span>
  <input v-model="name" type="text"></input>
  <input v-model="age" type="number"></input>
  </div>
  <HelloWorld/>
</template>

<style scoped>

.bold{
  font-weight: bolder;
}
.text-red{

  color: red;
}

.text-green{
  color:green;
}

input{
  margin:10px;
  border-radius: 5px;
}
button{
  padding: 10px;
  width: 5rem;
  background-color: red;
  border-color: darkgray;
}
div{
  display: flex;
}

</style>

