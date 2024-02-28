<script setup>
import main_page from './components/main_page.vue'
import top_buttons from './components/top_buttons.vue';
import answers_component from './components/answers_component.vue'
</script>

<template class="app">
  <main_page/>
  <top_buttons/>
  <div class="question-image">
    <img src="./assets/task_img.png" alt="Task-image">
  </div>
  <div class="answers">
  <answers_component/>
</div>
</template>

<style scoped>
  * {
    margin: 0;
    padding: 0;    
    width: 90%;
    margin: 0 auto;
  }

  .app{
    overflow-y: hidden;
  }

  .question-image {
    display: grid;
    place-items: center;
    position: absolute;
    width: auto;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);    
  }
  .question-image img {
    width: 50%;
    height: 100;
    min-width: 400px;
  }

  .answers {
  place-items: center;
  justify-content: center;
  overflow: hidden;
  height: 100%;
  }

</style>
