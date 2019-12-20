<template>
  <section>
    <b-field label="Provinsi" label-position="on-border">
      <b-select placeholder="Pilih Provinsi Anda" expanded v-model="province">
        <option :key="key" :value="province.name" v-for="(province, key) in provinces">{{province.name}}</option>
      </b-select>
    </b-field>
    <b-field label="Kabupaten / Kota" label-position="on-border" v-model="city">
      <b-select placeholder="Pilih Kabupaten / Kota Anda" expanded>
        <option :key="key" :value="city.name" v-for="(city, key) in cities">{{city.name}}</option>
      </b-select>
    </b-field>
    <b-field label="Kecamatan" label-position="on-border" v-model="district">
      <b-select placeholder="Pilih Kecamatan Anda" expanded>
        <option :key="key" :value="district.name" v-for="(district, key) in districts">{{district.name}}</option>
      </b-select>
    </b-field>
    <b-field label="Pilih Lokasi" label-position="on-border">
      <b-select expanded v-model="location">
        <option value="on-site">Di Luar KUA</option>
        <option value="in-site">Di KUA</option>
      </b-select>
    </b-field>
    <b-field label="Pilih Tanggal" label-position="on-border" grouped>
      <b-datepicker
        placeholder="Klik untuk memilih tanggal" expanded
        icon="calendar-today" v-model="predictedTime">
      </b-datepicker>
      <b-timepicker
        placeholder="Klik untuk memilih waktu"
        :min-time="minTime"
        :max-time="maxTime" v-model="predictedTime">
      </b-timepicker>
    </b-field>
  </section>
</template>

<script>
  export default {
    name: "Location",
    data: () => {
      const minTime = new Date()
      const maxTime = new Date()

      minTime.setHours(9)
      minTime.setMinutes(0)
      maxTime.setHours(17)
      maxTime.setMinutes(0)

      const predictedTime = new Date()

      predictedTime.setHours(9)

      return {
        provinces: [
          {
            name: 'Jawa Timur',
            cities: [
              {
                name: 'Surabaya',
                districts: [
                  {
                    name: 'Gubeng'
                  }
                ]
              }
            ]
          }
        ],
        province: '',
        city: '',
        district: '',
        location: 'on-site',
        predictedTime,
        minTime,
        maxTime
      }
    },
    computed: {
      cities: function () {
        const province = this.provinces.find(_ => _.name === this.province)
        return province ? province.cities : []
      },
      districts: function () {
        const city = this.cities.find(_ => _.name === this.city)
        return city ? city.districts : []
      }
    },
  }
</script>

<style scoped>

</style>
