<template>
  <section class="section">
    <div class="container">
      <h2 class="subtitle">Dokumen yang harus dibawa</h2>
      <ul style="list-style: circle">
        <li :key="key" v-for="(document, key) in documents">{{document}}</li>
      </ul>
    </div>
  </section>
</template>

<script>
  export default {
    name: "Confirm",
    data: () => ({
      documents: [
        'N1 - Surat Keterangan Untuk Nikah (Didapat dari Kelurahan)',
        'N2 - Surat Keterangan Asal Usul (Didapat dari Kelurahan)',
        'N4 - Surat Keterangan Tentang Orang Tua',
        'N5 - Surat Izin Orang Tua (Jika calon pengantin umurnya dibawah 21 tahun)',
        'Surat Akta Cerai (Jika calon pengantin sudah cerai)',
        'Surat Izin Komandan (Jika calon pengantin TNI atau POLRI)',
        'Surat Akta Kematian (Jika calon pengantin duda/janda ditinggal mati)'
      ]
    })
  }
</script>

<style scoped>

</style>
