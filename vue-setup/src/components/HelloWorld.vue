<template>
  <div class="hello">
    <div :class="clicked ? changeBg : changeBg2">
      <h1>La suma es igual a {{ sum }}</h1>
      <h1>La palabra invertida {{ word }} es {{ reverseWord() }}</h1>
      <h1 v-if="show">Si la variable show es {{ show }}, este texto se mostrara por pantalla</h1>
      <h1 v-if="!show">Si la variable show es {{ show }}, este texto se mostrara por pantalla</h1>
      <button @click="changeBool">Cambiar el valor de la variable <strong>show</strong></button>

      <h1 v-show="!show">v-show da el valor display:none</h1>

      <ul>
        <li v-for="post in posts" :key="post">{{ post.titulo }} - {{ post.descripcion }} - {{ post.contenido }}</li>
      </ul>

      <button @click="clickButton">Change background color</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      sum: 2 + 2,
      word: 'hola',
      show: true,
      posts: [
        { titulo: 'Titulo 1', descripcion: 'Descripcion 1', contenido: 'Contenido 1' },
        { titulo: 'Titulo 2', descripcion: 'Descripcion 2', contenido: 'Contenido 2' },
        { titulo: 'Titulo 3', descripcion: 'Descripcion 3', contenido: 'Contenido 3' }
      ],
      clicked: false,

      changeBg: 'change-bg',
      changeBg2: 'change-bg2'
    }
  },
  methods: {
    reverseWord(){
      return this.word.split('').reverse().join('')
    },

    changeBool(){
      if(this.show)
        this.show = false
      else
        this.show = true
    },

    clickButton(){
      this.clicked = !this.clicked
    }
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
  display: block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.change-bg{
  background-color: #9DA3A4;
}

.change-bg2{
  background-color: #000;
}
</style>
