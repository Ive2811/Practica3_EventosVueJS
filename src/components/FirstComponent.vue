<template>
  <div class="root">
        <h1>Ingrese una tecla </h1><input @keydown="showKey" class="inputStyle">
          <p>La tecla presionada es: <keyPress :class="style">{{key}}</keyPress></p> 
      </div>
</template>


<script>
  export default{
    name: 'Color de tecla',
    data(){
      return{
        key: ' ',
        style: ''
      }
    },
    methods:{
      showKey(event){
        const Numbers = /\d/;
        const Letters = /\w/;
        const key = event.key

        if(Numbers.test(key)){
          this.style='numeros'

        }else if(Letters.test(key) && key.length == 1){
          this.style='Letras'
        }else{
          this.style='caracteres'
        }
        this.key = key
      }
    }
  }
</script>
<style>

.root{
  background-color: lightblue;
}
h1{
  background-color: lightblue;
  color:blue;
  font-family:cursive;
}
p{
   color:blue;
  font-family:cursive;
  background-color: lightblue;
}
.inputStyle{
  background-color: lightgreen;
  height: 3vh;
  border-color: black;
}
keyPress{
  font-size:40px
}
keyPress.Letras{
  color:green;
  
}
keyPress.numeros{
  color:red;
  
}
keyPress.caracteres{
  color:yellow;
}
</style>