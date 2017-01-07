<template>
  <p class="radio">
    <label>
      <input :name="name" type="radio" :value="value" />
      <slot></slot>
    </label>
  </p>
</template>

<script>
  export default {
    name: 'RadioOption',
    props: ['name', 'value']
  }
</script>
