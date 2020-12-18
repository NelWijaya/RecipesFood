<template>
  <div class="about mt-5 pt-5">
    <div class="container pb-5">
      <section>
        <div class="row">
          <div class="col-12">
            <h1>About</h1>
          </div>
        </div>
        <div class="row mt-5">
          <div class="col-12 col-md-6">
            <img
              src="../assets/us.jpg"
              class="img-fluid"
              alt="Responsive image"
            />
          </div>
          <div class="col-12 col-md-6 py-3">
            <h3 class="mt-3">About Recipes Food</h3>
            <p>
              Merupakan website penyedia recipes terbaik mulai dari dalam negeri
              hingga luar negeri. Tunggu apa lagi, ciptakan senyum keluarga
              tercinta anda melalui masakan cinta hati mu.
            </p>
            <p>
              Memasak tidaklah sesulit yang kita bayangkan, dapur adalah teman
              kita. Tuanglah secercah kisah cerita dalam makanan kalian, dan
              biarkan orang merasakan kisah kamu.
            </p>
          </div>
        </div>
      </section>

      <section>
        <div class="row mt-5 pt-5">
          <div class="col-12  mb-5">
            <h1>Our Team</h1>
          </div>
        </div>
        <div class="row">
          <div class="col-12 col-md-4">
            <div class="card">
              <img src="../assets/ishack.png" class="card-img-top"/>
              <div class="card-body">
                <h5>Ishack Isodorus</h5>
                <h6>(00000036532)</h6>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-4">
            <div class="card">
              <img src="../assets/ruben.png" class="card-img-top"/>
              <div class="card-body">
                <h5>Ruben Raferty</h5>
                <h6>(00000036532)</h6>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-4">
            <div class="card">
              <img src="../assets/neldy.png" class="card-img-top"/>
              <div class="card-body">
                <h5>Neldy Wijaya</h5>
                <h6>(00000036532)</h6>
                <!-- <p class="card-text">
                  
                </p> -->
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {
  },
};
</script>

<style scoped>
.card{
  box-shadow: 0 6px 10px rgba(0,0,0,.08), 0 0 6px rgba(0,0,0,.05);
  transition: .3s transform cubic-bezier(.155,1.105,.295,1.12),.3s box-shadow,.3s -webkit-transform cubic-bezier(.155,1.105,.295,1.12);
}

.card:hover{
  transform: scale(1.05);
}
</style>