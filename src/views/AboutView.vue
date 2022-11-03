<script setup lang="ts">
import { ref } from "vue";

const count = ref(0);

const ready = ref(false);

const user = ref({
  name: "Andrew",
  email: "andrew@test.com",
});
user.value.email = "andrew@example.com";

function log() {
  alert("Show this alert");
}

var myObj = {
  name: "Pallabi",
  age: 22,
  weight: 58,
};

// Window.localStorage
let myObj_serialized = JSON.stringify(myObj);

localStorage.getItem(myObj_serialized);
console.log(localStorage);

let myObj_deSerialized = JSON.parse(myObj_serialized);

console.log(myObj_deSerialized);

localStorage.setItem("myCat", "Tom");

const cat = localStorage.getItem("myCat");
console.log(cat);

localStorage.removeItem("myCat");
console.log(localStorage);
</script>

<template>
  <div class="about">
    <div class="topnav">
      <button @click="log">Alert Button</button>
    </div>
    <div class="btn2">
      <button @click="count++">{{ count }}</button>
    </div>
    <div class="btn3">
      <button @click="ready = !ready">toggle</button>
    </div>
    <h1 v-if="ready">Vue is awesome! 😀</h1>
    <h1 v-else>Oh no 😢</h1>
    <h1>{{ user.email }}</h1>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  .topnav {
    padding-right: 10px;
    padding-left: 10px;
  }
  .btn2 {
    padding-right: 10px;
    padding-left: 10px;
  }
  .btn3 {
    padding-right: 10px;
    padding-left: 10px;
  }
}
</style>
