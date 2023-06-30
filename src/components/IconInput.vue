<script setup>
const {variant,position, icon}=defineProps(['variant','position','icon'])
let label = 0




</script>

<template>
    <div class="input">
        <label for="input">Label </label>
        <br/>
       <div class="inputContainer">

        <font-awesome-icon v-if="position == 'left'" :icon="['fas',icon]" class="icon"/>
        

        <input 
            class="textInput" 
            type="text" 
            placeholder="Placeholder" 
            name="input" 
            :class="variant" 
        >
        
        <font-awesome-icon 
            v-if="position == 'right'" 
            :icon="['fas',icon]" 
            class="icon2"
        />
        
       </div>
        
    </div>
</template>

<style scoped>
.inputContainer{
    display: flex;
    align-items: center;
    width:fit-content;
    padding: 0px 5px; 
    height:fit-content;
    border-radius: 10px;
}

.textInput{
    height:40px;
    border-radius: 10px;
    padding: 5px 0px;
    border: 1px solid black;
}

.textInput::placeholder{
    color: rgb(67, 66, 66);
}
.textInput:focus{
    border: none;
}

.left{
    padding-left: 25px;
    padding-right: 5px ;
}
.right{
    padding-right: 25px;
    padding-left: 5px;
}


.icon{
    position: absolute;
    margin-left: 5px;
    
}
.icon2{
    transform: translateX(-25px);
}


</style>    