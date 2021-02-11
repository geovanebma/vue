<!-- alurapic/src/components/shared/painel/Painel.vue -->

<template>

  <div class="painel">

    <h2 class="painel-titulo" @dblclick="visivel = !visivel">{{ titulo }}</h2>
    <transition name="painel-fade">
      <div class="painel-conteudo" v-show="visivel">
        <slot></slot>
      </div>
    </transition>

  </div>

</template>

<script>

export default {

   props: ['titulo'],

   data() {

       return {

           visivel: true
       }
   }

}

</script>

<style scoped>
/* scoped faz que o que estiver em *{}, seja preenchido pelo que esta apenas dentro da tag style abaixo, ou seja, as classes painel */
   .painel {
    padding: 0 auto;
    border: solid 2px grey;
    display: inline-block;
    margin: 5px;
    box-shadow: 5px 5px 10px grey;
    width: 200px;
    height: 100%;
    vertical-align: top;
    text-align: center;
  }

  .painel .painel-titulo {
    text-align: center;
    border: solid 2px;
    background: lightblue;
    margin: 0 0 15px 0;
    padding: 10px;
    text-transform: uppercase;
  }

  *{
      box-shadow: 5px 5px 5px #000;
  }

  .painel-fade-enter, .painel-fade-leave-active{
    opacity: 0;
  }

  .painel-fade-enter-active, .painel-fade-leave-active{
    transition: opacity 0.4s;
  }

/*painel-fade-enter - antes do elemento ser incluído ou removido, o estado atual*/
/*painel-fade-leave-active - quando o elemento esta sendo incluído*/
/*painel-fade-enter-active - quando o elemento esta sendo removido*/
</style>