<template>
  <div class="hello">
    <h1>Final: Stefania Albornoz Ibañez</h1>
    <hr>
    <div style="margin: 20px;">
      <label for="text">Ingrese un texto:</label>
      <input type="text" id="text" style="margin: 10px; height: 25px;" v-model= "texto">
    </div>
    <p>cantidad: {{texto.length}}</p>
    <p>{{ texto | codificar }} (Codificado)</p>
    <p>{{ texto.toUpperCase() }} (Mayúsculas)</p>
    <p>{{ texto.toLowerCase() }} (Minúscula)</p>
    <p>{{ texto | intercalarMayusculas }} (Mayúsculas/Minúscula)</p>
    <p>{{ texto | intercalarMinusculas }}(Minúscula/Mayúsculas)</p>


    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      texto: ''
    }
  },
  filters: {

    codificar(texto) {
      let textoCodif = texto.toLowerCase().split('')
      textoCodif.forEach((letra, index) => {
        if(letra === 'a') {
          textoCodif[index] = 'u'
        }
        else if (letra === 'e') {
          textoCodif[index] = 'o'         
        }
        else if (letra === 'o') {
          textoCodif[index] = 'e'
        }
        else if (letra === 'u') {
          textoCodif[index] = 'a'
        }
        index++
      });
      return textoCodif.join('')
    }, 

    intercalarMayusculas(texto) {
      let text = texto.split('')
      text.forEach((letra, index) => {
        if ((index === 0) || (index%2 === 0)) {
          text[index] = text[index].toUpperCase()  
        }
        else if (index%2 === 1) {
          text[index] = text[index].toLowerCase()  
        }
      })
      return text.join('')
      },

      intercalarMinusculas(texto) {
      let text = texto.split('')
      text.forEach((letra, index) => {
        if ((index === 0) || (index%2 === 0)) {
          text[index] = text[index].toLowerCase()  
        }
        else if (index%2 === 1) {
          text[index] = text[index].toUpperCase()  
        }
      })
      return text.join('')
      },

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
