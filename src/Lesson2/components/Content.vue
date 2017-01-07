<template>
  <div class="row">
    <div v-for="item in listOptions">
      <Post :title="item.title" :content="item.description" />
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Content',

    components: {
      Post: require('./Post.vue')
    },

    data() {
      return {
        listOptions: [
          { title: 'Lorem ipsum dolor', description: 'Alias facere dignissimos excepturi ea dolorem porro eaque.' },
          { title: 'Alias facere dignissimos', description: 'sit amet, consectetur adipisicing elit.' },
          { title: 'onsectetur adipisicing', description: 'nam ipsa amet quia iusto mollitia ipsum ipsam perspiciatis.' },
          { title: 'facere dignissimos excepturi', description: 'sit amet, consectetur adipisicing elit.' },
          { title: 'mollitia ipsum ipsam ', description: 'sit amet, consectetur adipisicing elit.' },
        ]
      }
    }
  }
</script>
