<template>
  <div id="app" class="container">

    <nav>
      <a href="javascript:void(0)" :class="navClass('lesson1')" @click="currentLesson = 'lesson1'">Lesson 1</a>
      <a href="javascript:void(0)" :class="navClass('lesson2')" @click="currentLesson = 'lesson2'">Lesson 2</a>
      <a href="javascript:void(0)" :class="navClass('lesson3')" @click="currentLesson = 'lesson3'">Lesson 3</a>
    </nav>

    <component :is="currentLesson" />
  </div>
</template>

<script>
  import Lesson1 from './Lesson1/Index.vue'
  import Lesson2 from './Lesson2/Index.vue'
  import Lesson3 from './Lesson3/Index.vue'

  export default {
    name: 'app',

    components: { Lesson1, Lesson2, Lesson3 },

    data () {
      return {
        currentLesson: 'lesson1',
      }
    },

    methods: {
      navClass(currentLesson) {
        return currentLesson === this.currentLesson
          ? 'btn btn-success'
          : 'btn btn-default'
      }
    }
  }
</script>

<style scoped>
  nav {
    margin: 40px 0;
  }
</style>
