<template>
  <div class="container">
    <div class="row">
      <div class="col-md-9 col-md-offset-3"><main-header /></div>
      <div class="col-md-3">
        <Sidebar />
      </div>
      <div class="col-md-9">
        <main-content />
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Main',

    components: {
      'main-header': require('./components/Header.vue'),
      'main-content': require('./components/Content.vue'),
      Sidebar: require('./components/Sidebar.vue')
    }
  }
</script>
