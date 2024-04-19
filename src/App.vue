<template>
  <!-- <div v-show="showName">
    Nome: {{ firstName }}<br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="accessLevel === 'admin'">Usuário Admin</div>
  <div v-else-if="accessLevel === 'marketing'"> UsuárioMarketing</div>
  <div v-else-if="accessLevel === 'user'"> Usuário User</div> -->
  <div>
    <TheHeader v-if="showHeader">

      <template v-slot:title>Home</template>
      <template v-slot:description>Home2</template>
      home3
      
    </TheHeader>
    <br>
    <BaseCard/>
    <br>
  <button @click="showHeader=!showHeader">Ativar e desativar header</button>
  <br>
  <input v-model="newName" type="text">
  <br>
    <h1 :class="{ 'title': true, 'title-home': isHome }">
      curso Vue3
    </h1>

    <p :class="pClass">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem excepturi eum, vel libero qui
      fugiat doloribus at
      illum doloremque fuga dolorum. Doloremque illum qui nisi. Dolorum veritatis vel nulla totam.</p>

    <p :style="styleClass">Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit perspiciatis deserunt,
      laudantium ratione fugit nobis vitae, tempore amet iste iure magnam non recusandae dolores doloremque quibusdam
      omnis eius, expedita eligendi.</p>

    <img v-bind:src="imgSrc" v-bind:alt="imgAlt">

    <div class="todos-item" v-for="(obj, index) in todos" :key="index">
      <img v-if="obj.imgSrc1" :src="obj.imgSrc1" v-bind:alt="obj.altName">
      {{ index }} - {{ obj.title }}
    </div>
  </div>

  <div>
    One-way data binding <br />
    Two-way data binding<br />
    v-model -> formularios
  </div>

  <br />
  <br />

  <div>
    <label for="">Nome</label><br>
    <input v-model="nome" type="text" value="Jon Snow"><br>
    {{ nome }}
  </div>
  <label for="">Sports</label><br>
  <select name="" id="" v-model="sports">
    <option value="">Escolha</option>
    <option value="futebol">Futebol</option>
    <option value="skate">Skate</option>
    <option value="tenis">Tenis</option>
  </select><br>
  {{ sports }}

  <div>
    <label for="">Newsletter</label><br>
    <input v-model="newsletter" type="radio" value="sim">Sim
    <input v-model="newsletter" type="radio" value="nao">não
    <br>
    {{ newsletter }}
    <br>
    <label for="">Contrato</label><br>
    <input v-model="contract" type="checkbox">Aceita nosso termos...
    <br>
    {{ contract }}
    <br>
    <label for="">Cores que você mais gosta</label><br>
    <input v-model="colors" type="checkbox" value="azul">Azul
    <br>
    <input v-model="colors" type="checkbox" value="amarelo">Amarelo
    <br>
    {{ colors }}

    <div>
      <button @click="clicando">Clicar</button>
    </div>
    <br>

    <div @mouseover="onMouseOver" @mouseout="onMouseOut()">
      Mouse over
    </div>
    <br><br>
    <form action="https://www.google.com.br" @submit.prevent="onSubmit">
      <input type="text" @keyup="onKeyUp"><br>
      <input type="text" @keypress="onKeyPress"><br>
      <button type="submit">Enviar</button>
    </form>

  </div>

  <div>
    {{ fulName }}<br>
    <br>
    <h2>Todos</h2>
    <br>
    <div v-for="(todo, index) in todos" :key="index">

      <input v-model="todo.completed" type="checkbox">
      {{ todo.title }}

    </div>
    <h2>Todos List em aberto</h2><br>
    <div v-for="(todo, index) in uncompletedTodos" :key="index">
      {{ todo.title }} <span>{{ todo.completed }}</span>
    </div>
  </div>

  <h2>Todos List completas</h2>
  <br>
  <div v-for="(todo, index) in completedTodos" :key="index">
    {{ todo.title }} <span>{{ todo.completed }}</span>
  </div>

  <div>
    <p>Watch:</p>
    <input v-model="nameWatch" type="text" name="" id=""><br>
    {{ nameWatch }}
  </div>

  <br><br><br>

  <select v-model="pageCount" name="" id="">
    <option value="5">5</option>
    <option value="10">10</option>
    <option value="15">15</option>
  </select>
  <br>
  <br>
  {{ pageCount }}
  <br>
  <input v-model="user.first_name" type="text"><br>
  <input v-model="user.last_name" type="text"><br>
  {{ user.first_name }}{{ user.last_name }}

</template>

<script>
import BaseCard from './components/BaseCard.vue';
import TheHeader from './components/TheHeader.vue';



export default {
  name: 'App',
  components:{TheHeader,BaseCard},

  data() {
    return {
      user: {
        first_name: '',
        last_name: '',
        showHeader:true
      },
      nameWatch:'',
      newName: 'Teste',
      pageCount:5,
      contract: false,
      colors: [],
      newsletter: '',
      nome: 'Jon Snow',
      classVar: 'title',
      sports: 'futebol',
      isHome: false,
      showHeader: true,
      pClass: ['text', 'title-home'],
      styleClass: { 'color': 'aqua' },
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
  },
  methods: {
    clicando($evt) {
      console.log('Clicou', $evt)
    },
    onMouseOver($evt) {
      console.log('mouse over', $evt)
    },
    onMouseOut($evt) {
      console.log('mouse out', $evt)
    },
    onSubmit($evt) {
      console.log('submit', $evt)
    },
    onKeyUp($evt) {

      console.log('onKeyUp', $evt)

    },
    onKeyPress($evt) {

      console.log('onKeyPress', $evt.key)

    },

    saveUserName(){
      console.log('Ajax')
        console.log(this.nameWatch);
    },
    changePage(){
      console.log('Ajax ChangePage')
    },

  },
  // HOOKS
  // beforeUpdate(){
  //   console.log('beforeUpdate',this.newName)
  // },
  // updated(){
    
  //   console.log('update',this.newName)
  // },
  // beforeCreate(){

  //   console.log('beforeCreate')
  //   console.log('Estado:',this.newName)
  //   console.log('DOM:', this.$el)
  // },
  // created(){
    
  //   console.log('created')
  //   console.log('Estado:',this.newName)
  //   console.log('DOM:', this.$el)

    
  // },
  
  // beforeMount(){
    
  //   console.log('beforeMount')
  //   console.log('Estado:',this.newName)
  //   console.log('DOM:', this.$el)


  // },
  // mounted(){
    
  //   console.log('mounted')
  //   console.log('Estado:',this.newName)
  //   console.log('DOM:', this.$el)


  // },
  watch: {
    nameWatch(vl){
        if(vl.length >=3){
          this.saveUserName()
        }
    },
    pageCount(){
      this.changePage();
    },
    user:{
      handler(){
        
        console.log('User alterado')
      },
      deep:true
    }
  },

  computed: {
    fulName() {
      return `${this.user.first_name} ${this.user.last_name}`
    },

    uncompletedTodos() {
      return this.todos.filter(todo => !todo.completed);
    },
    completedTodos() {
      return this.todos.filter(todo => todo.completed);

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

.text {
  color: yellow;
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
