<template>
  <div class=" card-title">
     <h5 class="card-title">{{namakaryawann.nama_karyawan}}</h5>
    <!-- <p class="card-title ">{{namakaryawann.tanggal_awal}}
     {{namakaryawann.tanggal_akhir}}</p>
     <p class="card-text">
         {{namakaryawann.total_kehadiran}}</p> -->
     </div>
     
     
</template>

<script>
export default {
 name:'Namakaryawans',
 props: ['namakaryawann']
}
</script>

<style>

</style>