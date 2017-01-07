<template>
  <div>
    <select class="form-control" :name="name">
      <option hidden disabled selected>{{ placeholder }}</option>
      <option v-for="item in options" :value="item.value">{{ item.label }}</option>
    </select>
  </div>
</template>

<script>
  export default {
    name: 'SelectOptionGroup',
    props: ['placeholder', 'name', 'options', 'value']
  }
</script>
