<template>

    <div>
        <h1>{{ titulo }}</h1>
        <button @click="atualizarComponente()">Atualizar</button>
        <button @click="conteudo = 'Home'">Home</button>
        <button @click="conteudo = 'Publicar'">Publicar Vaga</button>
        <p>Propriedade com v-bind :class="$style['teste']" = {{ $style }}</p>
        <div :class="$style['teste']">Classe teste</div>
        <div>variavel data: {{ teste }}</div>
        <!-- <Home />
        <Publicar /> -->
        <KeepAlive>
          <component :is="conteudo" />
        </KeepAlive> 
    </div>

</template>

<script>
import PublicarVaga from '@/views/PublicarVaga.vue'
import Home from '@/views/Home.vue'

export default {
  name:'Content',
  components:{
      Home,
      Publicar: PublicarVaga,
  },
  methods:{
    atualizarComponente(){
        this.titulo += '*' 
    }
  },
  data: () => {
    return {
        teste: 'atualizei e comitei',
        titulo: 'Componente Conteudo',
        conteudo: 'Home'
    }
  },
  /*
  beforeCreate(){
    console.log('Antes de criar', this.teste)
  },
  
  created(){
    console.log('Criado', this.teste)
  },
  
  beforeMount(){
    console.log('antes de montar')
  },
  mounted(){
    console.log('Montado')
  },
  beforeUpdate(){
    console.log('Antes de Atualizar')
  },
  updated(){
    console.log('Atualizado')
  },
  beforeUnmount(){
    console.log('Antes de desmontar/destruir')
  },
  unmounted(){
    console.log('Desmontado')
  },

  errorCaptured(){
    console.log('Erro capturado')
  },
  renderTracked(){
    console.log('Re-render rastreado')
  },
  renderTriggered(){
    console.log('Re-render acionado')
  },
  activated(){
    console.log('Ativado')
  },
  deactivated(){
    console.log('desativado')
  },
  async serverPrefetch() {
    console.log('pre-fetch data on server as it is faster than on the client')
  }
  */

}
</script>

<style module>
    .teste{
        background-color: chocolate;
    }
</style>