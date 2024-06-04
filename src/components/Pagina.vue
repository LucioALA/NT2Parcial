<template lang="html">

  <section class="src-components-pagina">
    <h1>Parcial NT2</h1><br>

<input type="text" id="texto" name="texto" v-model="texto"><br><br>
{{ texto }}<br>

cantidad caracteres: {{ texto.length }}<br>
1-{{ cambiarVocales() }}(codificado)<br> 
2-{{  aMayusculas()}}(mayusculas)<br> 
3-{{ aMinusculas()}}(minusculas)<br>
4-{{ intercalarTexto2()}}(mayusculas/minusculas)<br>
5-{{ intercalarTexto1()}}(minusculas/mayusculas)<br><br>


Respuestas: 1:c , 2:c, 3:a






  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-pagina',
    props: [],
    mounted () {

    },
    data () {
      return {

        texto: '',
        textoMayusculas: '',
       textoMinusculas: ''

      }
    },
    methods: {

      aMayusculas(){
        return this.texto.toUpperCase();

      },
      aMinusculas(){
        return this.texto.toLowerCase();

      },


     cambiarVocales() {
  let resultado = '';
  const minusculas = this.aMinusculas();

  for (let char of minusculas) {
    switch (char) {
      case 'a':
        resultado += 'u';
        break;
      case 'e':
        resultado += 'o';
        break;
      case 'i':
        resultado += 'i';
        break;
      case 'o':
        resultado += 'e';
        break;
      case 'u':
        resultado += 'a';
        break;
      default:
        resultado += char;
    }
  }

  return resultado;


},

intercalarTexto1() {
      let letras = this.texto.split(''); // Convertimos el texto en un array de caracteres


      for (let i = 0; i < letras.length; i++) {
        if (i % 2 === 0) {
          letras[i] = letras[i].toLowerCase();
        } else {
          letras[i] = letras[i].toUpperCase();
        }
      }
      return letras.join(''); // Unimos los caracteres de nuevo en un string
    },
    intercalarTexto2() {
      let letras = this.texto.split(''); // Convertimos el texto en un array de caracteres


      for (let i = 0; i < letras.length; i++) {
        if (i % 2 === 0) {
          letras[i] = letras[i].toUpperCase();
        } else {
          letras[i] = letras[i].toLowerCase();
        }
      }
      return letras.join(''); // Unimos los caracteres de nuevo en un string
    }
  


    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-pagina {

  }
</style>
