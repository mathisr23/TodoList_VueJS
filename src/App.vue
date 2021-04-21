
<template>
  <div id="app">
     <section class="hero is-warning is-bold is-fullheight">
      <div class="hero-body">
          <todo-card />
          
      </div>

      <div class="hero-foot">
        <div class="container">
          <div class="content has-text-centered pb-5">
            <p>
              <strong>Atelier Mars 2021</strong>
            </p>
            <p>
              Découvrez comment styliser simplement votre ToDo list avec 
              <a class="has-text-primary" href="https://bulma.io/">
                <strong>Bulma</strong>
              </a> 
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>

import todoCard from './components/todo-card.vue'


export default {
  components: { todoCard },
  name: 'app',
  data () {
    return {
      msg: 'Hello, et bienvenue sur la demo TodoList en Vue.js!'
    }
  }
}
</script>

<style>
.hero-body{
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>