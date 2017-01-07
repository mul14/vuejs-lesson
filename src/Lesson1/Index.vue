<template>
  <div>
    <form action="" class="form-horizontal">

      <h3>Pilih Jurusan</h3>
      <div>
        <SelectOptionGroup
            placeholder="Pilih Jurusan"
            name="jurusan"
            :options="listJurusan"
        />
      </div>

      <h3>Pilih Bahasa Pemrogaman</h3>
      <RadioOptionGroup name="bahasa" :options="listOptions" />

      <div class="radio">
        <label>
          <input type="radio" name="bahasa" value="other" v-model="lainnya" />
          Lainnya
        </label>
        <label class="form-inline">
          <input type="text" name="bahasalain" class="form-control" :disabled="lainnya != 'other'" required />
        </label>
      </div>

      <p class="radio">
        <input type="submit" class="btn btn-success" />
      </p>

    </form>
  </div>
</template>

<script>
  export default {
    name: 'Lesson1',

    components: {
      SelectOptionGroup: require('./components/SelectOptionGroup.vue'),
      RadioOptionGroup: require('./components/RadioOptionGroup.vue')
    },

    data() {
      return {
        lainnya: false,

        listOptions: [
          { value: 'php', label: 'PHP' },
          { value: 'ruby', label: 'RUBY' },
          { value: 'python', label: 'Python' },
          { value: 'elixir', label: 'Elixir' },
          { value: 'golang', label: 'Golang' }
        ],

        listJurusan: [
          { value: 'SI', label: 'Sistem Informasi' },
          { value: 'TI', label: 'Teknik Informatika' },
          { value: 'TE', label: 'Teknik Elektro' },
          { value: 'TM', label: 'Teknik Mesin' },
          { value: 'TS', label: 'Teknik Sipil' }
        ]
      }
    }
  }
</script>
