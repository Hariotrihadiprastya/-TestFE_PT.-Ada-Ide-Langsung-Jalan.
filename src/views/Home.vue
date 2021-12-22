<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero/>   
       <div class="card text-dark bg-white " style="max-width: 30rem;">
      <div class="card-header font-weight-bold text-center bg-primary text-white">Faktur Gaji</div>
      <div class ="card-title">
     <div class="mb-2" v-for="namakaryawann in namakaryawan" :key="namakaryawann.id">
      <Namakaryawans :namakaryawann="namakaryawann"/>
      </div>
      <p class="text-secondary">01 Januari 2021 - 31 Januari 2021 </p>
      <p class="text-secondary">Masuk 22 Hari </p>
      
    </div>
  </div>
    </div>

    </div>
  
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import Namakaryawans from "@/components/Namakaryawans.vue";
import axios from "axios";





export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    Namakaryawans,
  },
 data(){
   return{
     namakaryawan:[]
   }
 },
  methods: {
    setnamakaryawan(data) {
      this.namakaryawan = data;
    }
  },
  mounted() {
      axios.get( 'https://boss.smartlink.id/salary/inquiry')
      .then((response)=>this.setnamakaryawan(response.data))
      .catch((error) => console.log(error)) 
  },
};
</script>
