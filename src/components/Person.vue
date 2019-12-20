<template>
  <section>
    <b-field label="Warganegara" label-position="on-border">
      <b-select placeholder="Pilih Kewarganegaraan Anda" expanded>
        <option value="indenesia">INDONESIA</option>
        <option value="asing">ASING</option>
      </b-select>
    </b-field>
    <b-field :label="'NIK Calon ' + name " label-position="on-border">
      <b-input placeholder="Isikan dengan NIK yang terdapat pada KTP"></b-input>
    </b-field>
    <b-field :label="'Nama Calon ' + name " label-position="on-border">
      <b-input placeholder="Isikan dengan Nama yang terdapat pada KTP"></b-input>
    </b-field>
    <b-field label="Tempat Lahir" label-position="on-border">
      <b-input placeholder="Isikan dengan Tempat Lahir yang terdapat pada KTP"></b-input>
    </b-field>
    <b-field label="Tanggal Lahir" label-position="on-border">
      <b-datepicker
        placeholder="Klik untuk memilih tanggal" expanded
        icon="calendar-today">
      </b-datepicker>
    </b-field>
    <b-field label="Status" label-position="on-border">
      <b-select expanded>
        <option :key="key" :value="status" v-for="(status, key) in statuses">{{status}}</option>
      </b-select>
    </b-field>
    <b-field label="Agama" label-position="on-border">
      <b-select expanded>
        <option value="islam">Islam</option>
        <option value="kristen">Kristen</option>
        <option value="katholik">Katholik</option>
        <option value="budha">Budha</option>
      </b-select>
    </b-field>
    <b-field label="Alamat">
      <b-input maxlength="200" type="textarea"></b-input>
    </b-field>
    <b-field label="Pekerjaan" label-position="on-border">
      <b-select expanded>
        <option value="tni">TNI</option>
        <option value="pengangguran">Belum Bekerja</option>
        <option value="rumah-tangga">Mengurus Rumah Tangga</option>
        <option value="pegawai-swasta">Pegawai Swasta</option>
      </b-select>
    </b-field>
    <b-field label="Nomor HP" label-position="on-border">
      <b-input placeholder="Isikan dengan nomer telepon"></b-input>
    </b-field>
  </section>
</template>

<script>
  export default {
    name: "Person",
    props: {
      name: {
        required: true,
        type: String
      }
    },
    data: () => ({

    }),
    computed: {
      statuses: function () {
        return this.name === 'Istri' ? [
          'Perawan',
          'Cerai Hidup',
          'Cerai Mati'
        ] : [
          'Beristri',
          'Jejaka',
          'Cerai Hidup',
          'Cerai Mati'
        ]
      }
    }
  }
</script>

<style scoped>

</style>
