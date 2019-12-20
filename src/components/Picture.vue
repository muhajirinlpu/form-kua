<template>
  <section class="columns">
    <b-field class="file column">
      <b-upload v-model="fileHusband" @input="some">
        <a class="button is-primary">
          <b-icon icon="upload"></b-icon>
          <span>Upload foto Calon Suami</span>
        </a>
      </b-upload>
    </b-field>
    <b-field class="file column">
      <b-upload v-model="fileWife">
        <a class="button is-primary">
          <b-icon icon="upload"></b-icon>
          <span>Upload Foto Calon Istri</span>
        </a>
      </b-upload>
    </b-field>
  </section>
</template>

<script>
  export default {
    name: "Picture",
    data: () => ({
      fileHusband: {
        name: ''
      },
      fileWife: {
        name: ''
      }
    }),
    methods: {
      some(e) {
        console.log('run', e.target)
      }
    },
    watch: {
      fileHusband: {
        handler(file) {
          console.log(file instanceof File, file.target)
        },
        deep: true
      }
    }
  }
</script>

<style scoped>

</style>
