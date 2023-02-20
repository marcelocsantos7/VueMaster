<template>
  <div>
    <h1>Componente App</h1>
    <button @click="desmontarComponente()">Desmontar Componente Conteudo</button>
    <button @click="montarComponenteConteudo()">Montar Componente Conteudo</button>
    <Nav />
    <Content v-if="visibilidade"/>
  </div>
</template> 

<script>
import Nav from '@/components/layouts/Nav.vue'
import Content from '@/components/layouts/Content.vue'

export default {
  name:'App',
  components:{
    Nav,
    Content
  },
  data: () =>{
    return {
      visibilidade: true,
    }
  },
  methods: {
    desmontarComponente(){
      this.visibilidade = false
    },
    montarComponenteConteudo(){
      this.visibilidade = true
    }
  },
}
</script>

<style scoped>

</style>
