<template>
  <div class="section">
    <div class="container">
      <b-steps>
        <b-step-item label="Pilih Lokasi" icon="home" style="padding: 30px 0">
          <Location />
        </b-step-item>
        <b-step-item label="Suami" icon="account" style="padding: 30px 0">
          <Person name="Suami"/>
        </b-step-item>
        <b-step-item label="Istri" icon="account" style="padding: 30px 0">
          <Person name="Istri" />
        </b-step-item>
        <b-step-item label="Foto" icon="file-image" style="padding: 30px 0">
          <Picture />
        </b-step-item>
        <b-step-item label="Konfirmasi" icon="check" style="padding: 30px 0">
          <Confirm/>
        </b-step-item>
      </b-steps>
    </div>
  </div>
</template>

<script>
  import Location from "./components/Location";
  import Person from "./components/Person";
  import Picture from "./components/Picture";
  import Confirm from "./components/Confirm";

  export default {
    name: 'app',
    components: {
      Location,
      Person,
      Picture,
      Confirm
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
