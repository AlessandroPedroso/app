<template>
    <header class="header">

      <h1 v-if="$slots.title" class="title">
        <slot name="title"/>
      </h1>
      
      <h2 v-if="$slots.description" class="description">
        <slot name="description" />
      </h2>
      
      <slot />
    </header>
</template>

<script>
export default {
    name: 'TheHeader',

    mounted(){
      //  window.addEventListener('resize',this.resize)
      console.log(this.$slots)
       console.log('mounted:Montou')
    },

    beforeUnmount(){
    //Destruir as nossas libs
    //Eventos
    //Listeners
    window.removeEventListener('resize',this.resize)
    console.log('beforeUnmount')
  
  },
  unmounted(){
    
    console.log('unmounted')
  },

  methods:{
    resize($evt){
        console.log($evt)
    }
  }
}
</script>

<style scoped>
.header {
    background: #000;
    color: #fff;
}
</style>