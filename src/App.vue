<script setup>
import Navbar from './components/Navbar.vue'
import BaseInput from './components/BaseInput.vue'
import IconInput from './components/IconInput.vue'
import Multiline from './components/Multiline.vue'
import { ref } from 'vue';


const inputTypes = ['default', 'error']
const icons = ['cart-shopping', 'phone', 'lock', 'lock-open', 'magnifying-glass']
const row = ref(2)
</script>

<template>
  <div>
    <Navbar />
    <div class="contentBox" v-for="item in inputTypes">
      <BaseInput :variant="item" />
    </div>
    <div class="contentBox">
      <BaseInput :type="'disabled'" />
    </div>
    <div class="contentBox row">
      <div v-for="item in inputTypes">
        <BaseInput :variant="item" helperText="Some helper text" />
      </div>
    </div>
    <div class="contentBox row">
      <div v-for="item in icons">
        <IconInput variant="left" position="left" :icon="item"/>
      </div>
    </div>
    <div class="contentBox row">
      <div v-for="item in icons">
        <IconInput variant="right" position="right" :icon="item"/>
      </div>
    </div>
    <div class="contentBox row">
      
        <BaseInput size="sm" />
        <BaseInput size="md" />
        
        
        
      </div>
      <div class="contentBox">
  
        <BaseInput size="full" />
      </div>
      <div class="contentBox">
  
        <div class="buttons">
          <button @click="row++">Add Row</button>
          <button v-if="row >1" @click="row--">Eliminate Row</button>
        </div>
        <Multiline :row="row" />

      </div>
    </div>
</template>

<style scoped>
.contentBox {
  display: flex;
  flex-direction: column;
  margin: 3% ;
  gap: 20px;
}

.contentItem {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.row {
  flex-direction: row !important;
}
h4{
  margin-left: 50px;
  margin-top: 50px;
}

button {
  border: none;
  padding: 8px 12px;
  width: fit-content;
  border-radius: 5px;
  background-color: rgb(248, 123, 28);
  margin: 5px;
}
button:hover{
  box-shadow: 2px 2px 0px 0px rgba(0,0,0,0.75);
}

</style>
