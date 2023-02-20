<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <PesquisarVaga />
      </div>
    </div>

    <div class="row mt-5">
      <div class="col-4">
        <Indicador />
      </div>

      <div class="col-4">
        <Indicador />
      </div>

      <div class="col-4">
        <Indicador />
      </div>

    </div>
  </div>
</template>

<script>
import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue'
import Indicador from '@/components/comuns/Indicador.vue'
export default {
  name: 'Home',
  components: {
    PesquisarVaga,
    Indicador
  },
  activated() {
    console.log('Ativado')
  },
  deactivated() {
    console.log('desativado')
  },
  beforeUnmount() {
    console.log('Antes de desmontar/destruir')
  },
  unmounted() {
    console.log('Desmontado')
  },
}
</script>

<style scoped></style>