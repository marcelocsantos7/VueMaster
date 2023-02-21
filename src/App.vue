<template>
  <div>
    <!-- <button @click="desmontarComponente()">Desmontar Componente Conteudo</button>
    <button @click="montarComponenteConteudo()">Montar Componente Conteudo</button> -->
    <!-- <Nav @eventoQueSeraCapturadoNoPai="$event('texto 1', 125)"/> dessa forma, o evento do filho, ja é disparado
    inclusive, passando de volta, parametros pro componente filho -->
    <!-- <Nav @eventoQueSeraCapturadoNoPai="acao($event)"/>  dessa forma, utilizo um metodo do pai pra capturar 
      o evento do filho
    -->
    <VagasFavoritas />
    <Nav @navegar="componente = $event" />
    <Content v-if="visibilidade" :conteudo="componente" />
  </div>
</template> 

<script>
import Nav from '@/components/layouts/Nav.vue'
import Content from '@/components/layouts/Content.vue'
import VagasFavoritas from '@/components/comuns/VagasFavoritas.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Content,
    VagasFavoritas
},
  data: () => ({
    visibilidade: true,
    componente: 'Home'
  }),
}
</script>

<style scoped></style>
