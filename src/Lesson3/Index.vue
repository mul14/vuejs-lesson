<template>
  <div class="container">
    <div class="input-group">
      <input type="text" class="form-control input-lg" v-model="newTask" @keyup.enter="addNewTask">
      <span class="input-group-btn"><button class="btn btn-primary btn-lg" @click="addNewTask">Add New Task</button></span>
    </div>

    <div v-show="todoList.length ">
      <h3>Todo ({{ todoList.length }})</h3>

      <ul class="list-group">
        <li v-for="task in todoList" class="list-group-item clearfix">
          <div class="pull-left lead">
            {{ task.name }}
          </div>
          <div class="pull-right">
            <button class="btn btn-primary" @click="done(task)">Done</button>
          </div>
        </li>
      </ul>
    </div>

    <div v-show="doneList.length">
      <h3>Done ({{ doneList.length }})</h3>

      <ul class="list-group">
        <li v-for="task in doneList" class="list-group-item clearfix">
          <div class="pull-left lead">
            {{ task.name }}
          </div>
          <div class="pull-right">
            <button class="btn btn-default" @click="undone(task)">Undone</button>
            <button class="btn btn-default" @click="remove(task)">Remove</button>
          </div>
        </li>
      </ul>
    </div>

    <button v-show="todoList.length || doneList.length" @click="clear" class="btn btn-default">
      Clear all
    </button>

  </div>
</template>

<script>
  export default {
    name: 'Lesson3',

    data() {
      return {
        newTask: '',

        tasks: [
          { name: 'Beli baju di mall', done: false },
          { name: 'Tidur siang', done: false },
          { name: 'Makan kentang', done: true },
          { name: 'Baca komik', done: false },
          { name: 'Buka pintu', done: true },
        ]
      }
    },

    computed: {
      doneList() {
        return this.tasks.filter(task => task.done)
      },
      todoList() {
        return this.tasks.filter(task => !task.done)
      }
    },

    methods: {
      addNewTask() {
        this.tasks.push({
          name: this.newTask,
          done: false
        })
        this.newTask = ''
      },

      done(task) {
        task.done = true
      },

      undone(task) {
        task.done = false
      },

      remove(task) {
        const index = this.tasks.indexOf(task)
        this.tasks.splice(index, 1)
      },

      clear() {
        this.tasks = []
      }

    }
  }
</script>

<style scoped>
  .container {
    margin-top: 40px;
  }
</style>
