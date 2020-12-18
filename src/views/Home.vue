<template>
  <div class="home">
    <section>
      <div class="jumbotron">
        <div class="container">
          <section class="mt-md-2">
            <div class="row">
              <div class="col-12 col-lg-6 ml-auto mt-md-0">
                <h1 class="display-4">Welcome, cooking lovers</h1>
                <p class="lead my-3 px-2">
                  Berbagi kisah, pengalaman, dan rindu dengan orang terdekat
                  kalian melalui masakan.
                </p>
                <a class="btn btn-primary btn-lg mt-2" href="#" role="button"
                  >Mulai Masak</a
                >
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>

    <Chicken />
    <Pizza />

    <hr>
    <section>
      <div class="container mb-5">
        <div class="row">
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
             <router-link class="nav-link btn btn-primary more-us" to="/about">More About Us</router-link>
          </div>
        </div>
      </div>
    </section>

    <hr>
    <section>
      <div class="container">
        <div class="row">
          <div class="m-auto">
            <h3>CONTACT US</h3>
          </div>
        </div>
        <div class="row mt-3">
          <div class="col-12 col-md-6">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15864.155754339328!2d106.615453!3d-6.2586013!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x50c7d605ba8542f5!2sMultimedia%20Nusantara%20University!5e0!3m2!1sen!2sid!4v1608011490399!5m2!1sen!2sid"
              width="100%"
              height="300"
              frameborder="0"
              style="border: 0"
              allowfullscreen=""
              aria-hidden="false"
              tabindex="0"
            ></iframe>
          </div>
          <div class="col-12 col-md-6">
            <form>
              <div class="form-group">
                <label for="exampleFormControlInput1">Nama Lengkap</label>
                <input
                  class="form-control"
                  id="exampleFormControlInput1"
                  placeholder="Fullname"
                />
              </div>
              <div class="form-group">
                <label for="exampleFormControlInput1">Email</label>
                <input
                  type="email"
                  class="form-control"
                  id="exampleFormControlInput1"
                  placeholder="name@example.com"
                />
              </div>
              <div class="form-group">
                <label for="exampleFormControlTextarea1">Pesan</label>
                <textarea
                  class="form-control"
                  id="exampleFormControlTextarea1"
                  rows="3"
                ></textarea>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>

    
  </div>
</template>

<script>
import axios from "axios";
import Pizza from "@/components/Pizza.vue";
import Chicken from "@/components/Chicken.vue";

export default {
  name: "Home",
  components: {
    Pizza,
    Chicken,
  },

  data() {
    return {
      recipes: [],
    };
  },
  mounted() {
    axios
      .get(
        "https://api.edamam.com/search?q=chicken&app_id=cfe334bb&app_key=9bdacd637856379f6fc33e295cbc2b68"
      )
      .then((response) => {
        this.recipes = response.data.hits;
        console.log(this.recipes);
      })
      .catch((error) => {
        console.log("Error", error);
      });
  },
};
</script>

<style scoped>
.jumbotron {
  background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
    url("../assets/backgroundhome.png");

  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
  color: white;
  border-radius: 0;
  min-height: 100vh;
  height: 100vh;
}

form label {
  float: left;
  margin-top: 5px;
}
section{
  margin-top: 50px;
}

.more-us{
  width: 200px;
  margin: auto;
}
</style>
