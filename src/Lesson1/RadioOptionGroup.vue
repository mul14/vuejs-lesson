<template>
  <div>
    <div v-for="item in options">
      <RadioOption :name="name" :value="item.value">
        {{ item.label }}
      </RadioOption>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'RadioOptionGroup',

    components: {
      RadioOption: require('./RadioOption.vue')
    },

    props: ['name', 'options']
  }
</script>
