<template>
  <!-- <div v-show="showName">
    Nome: {{ firstName }}<br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="accessLevel === 'admin'">Usuário Admin</div>
  <div v-else-if="accessLevel === 'marketing'"> UsuárioMarketing</div>
  <div v-else-if="accessLevel === 'user'"> Usuário User</div> -->
  <div>

    <h1 :class="{ 'title': true, 'title-home': isHome }">
      curso Vue3
    </h1>

    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem excepturi eum, vel libero qui fugiat doloribus at
      illum doloremque fuga dolorum. Doloremque illum qui nisi. Dolorum veritatis vel nulla totam.</p>

    <img v-bind:src="imgSrc" v-bind:alt="imgAlt">

    <div class="todos-item" v-for="(obj, index) in todos" v-bind:key="index">
      <img v-if="obj.imgSrc1" :src="obj.imgSrc1" v-bind:alt="obj.altName">
      {{ index }} - {{ obj.title }}
    </div>
  </div>


</template>

<script>



export default {
  name: 'App',

  data() {
    return {
      classVar: 'title',
      isHome: true,
      showHeader: true,
      firstName: 'Alessandro',
      lastName: 'Schuquel Pedroso',
      showName: false,
      accessLevel: 'admin',
      imgAlt: 'foto de perfil',
      imgSrc: 'https://placehold.co/150',
      todos: [
        {
          "userId": 1,
          "id": 1,
          "title": "delectus aut autem",
          "completed": false,
          "imgSrc1": "https://placehold.co/150",
          "altName": "Foto imagem"
        },
        {
          "userId": 1,
          "id": 2,
          "title": "quis ut nam facilis et officia qui",
          "completed": false,
          "imgSrc1": "https://placehold.co/150",
          "altName": "Foto imagem"
        },
        {
          "userId": 1,
          "id": 3,
          "title": "fugiat veniam minus",
          "completed": false,
          "imgSrc1": "https://placehold.co/150",
          "altName": "Foto imagem"
        },
        {
          "userId": 1,
          "id": 4,
          "title": "et porro tempora",
          "completed": true
        },
        {
          "userId": 1,
          "id": 5,
          "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
          "completed": false
        }
      ]
    }
  }
}
</script>

<style>
.title {
  font-size: 20px;
  color: blue;
}

.title-home {
  font-size: 40px;
  color: red;
}

.todos-item {
  background: #000;
  margin: 0 0 5px 0;
  padding: 3px 6px;
  color: white;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px;
}
</style>
