<script setup>
const {variant,type,helperText,size}=defineProps([
    'variant',
    'type',
    'helperText',
    'size',
    
])
let label = 0
if (variant) {
   label = variant
}

if(type) {
    label = type
}
if(helperText){
    label = variant+ ' Helper Text'

}
if(size){
    label = 'size='+ size
}



</script>

<template>
    <div class="input">
        <label for="input">Label {{label}}</label>
        <br/>
        <input 
            class="textInput" 
            type="text" 
            placeholder="Placeholder" 
            name="input" 
            :class="[variant,size]" 
            :disabled="type == 'disabled'"
            
            
        >

        <p v-if="helperText">{{helperText}}</p>
       
    </div>
</template>

<style scoped>

.textInput{
    height:40px;
    border-radius: 10px;
    padding: 5px;
    margin-top: 5px;
    border: 2px solid rgb(102, 102, 102);
}
.textInput:hover{
    
    border: 2px solid rgb(67, 66, 66);
}
.textInput:hover::placeholder{
    color: rgb(67, 66, 66);
}

.default:focus{
    border:2px solid rgb(0, 136, 255) !important;
}
.default:focus::placeholder{
    color:rgb(0, 136, 255) ;
}

.md{
    width: 300px
}
.full{
    width: 100%;
}
.error{
    border:2px solid red;
}
.error::placeholder{
    color: red;
}
.error:focus{
    border:2px solid red !important;

}


.textInput:disabled{
    cursor: not-allowed;
    background-color: rgb(190, 190, 190);
    border: none !important ;

}
.textInput:disabled:hover{
    background-color: rgb(190, 190, 190);

}
p{
    font-size: 10px;
    margin-left: 10px;
    margin-top: 5px;
    color: #585858;
}
.error + p{
    color: red !important;
}
</style>    