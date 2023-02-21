<template>
  <div class="container mt-3">
    <KeepAlive>
      <component :is="conteudo" />
    </KeepAlive>
  </div>
</template>

<script>
import PublicarVaga from '@/views/PublicarVaga.vue'
import Home from '@/views/Home.vue'


export default {
  name: 'Content',
  props: {
    conteudo: {
      type: String,
      required: true
    }
  },
  components: {
    Home,
    Publicar: PublicarVaga,

  },
  methods: {
    atualizarComponente() {
      this.titulo += '*'
    }
  },
  data: () => {
    return {
      titulo: 'Componente Conteudo',
    }
  },
}
</script>

<style module>
.teste {
  background-color: chocolate;
}
</style>