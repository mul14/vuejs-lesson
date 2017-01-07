<template>
  <div id="app" class="container">

    <a href="javascript:void(0)" class="btn btn-success" @click="currentLesson = 'lesson1'">Lesson 1</a>
    <a href="javascript:void(0)" class="btn btn-success" @click="currentLesson = 'lesson2'">Lesson 2</a>
    <a href="javascript:void(0)" class="btn btn-success" @click="currentLesson = 'lesson3'">Lesson 3</a>

    <component :is="currentLesson" />
  </div>
</template>

<script>
  import Lesson1 from './Lesson1/Index.vue'
  import Lesson2 from './Lesson2/Index.vue'
  import Lesson3 from './Lesson3/Index.vue'

  export default {
    name: 'app',

    components: {
      Lesson1,
      Lesson2,
      Lesson3,
    },

    data () {
      return {
        currentLesson: 'lesson1',
      }
    }
  }
</script>
