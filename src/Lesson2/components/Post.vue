<template>
  <div class="col-md-4">
    <div class="panel panel-default">
      <div class="panel-heading">{{ title }}</div>
      <div class="panel-body">
        <p> {{ content }} </p>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Post',
    props: ['title', 'content']
  }
</script>
