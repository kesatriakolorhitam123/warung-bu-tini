<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="info">

    <div class="container">
    <b-navbar-brand class="navbar-brand font-pacifico"  href="#">Warung Bu Tini</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <router-link class="nav-link" to="/">Home</router-link>
        <router-link class="nav-link" to="/foods">Foods</router-link>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
<b-navbar-nav class="ml-auto">

            <li class="nav-item">
              <router-link class="nav-link" to="/keranjang">
              Keranjang
              <b-icon-bag/>
              <span class="badge badge-success ml-2">{{ updateKeranjang ? updateKeranjang.length : jumlah_pemesanans.length }}</span></router-link>
            </li>
           
         
</b-navbar-nav>
    </b-collapse>
    </div>
  </b-navbar>
</div>
 
</template>

<script>
import axios from "axios";
export default {
  name: "Navbar",
  data() {
      return {
          jumlah_pemesanans: []
      }
  },
  props: ['updateKeranjang'],
  methods: {
      setJumlah(data){
          this.jumlah_pemesanans = data
      }
  },
  mounted() {
       axios
    .get("http://localhost:3000/keranjangs")
    .then((response) => this.setJumlah(response.data))
    .catch((error) => console.log(error))
  }
};
</script>

<style>
</style>