<template>
    <footer class="bg-dark text-white py-5 mt-5">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-7 mr-auto information-footer">
            <b>Copyright&copy;2020 Kelompok 6</b>
            <p>
              <br />
              Recipes food merupakan website dimana para pengguna dapat melihat
              resep dengan kandungan kalori pada makanan tersebut.
            </p>
          </div>
          <div class="col-12 col-md-5 sosmed ml-auto">
            <a href="http://facebook.com/Edamam"
              ><i class="fa fa-facebook-official"></i
            ></a>
            <a href="http://twitter.com/#!/EdamamCo"
              ><i class="fa fa-twitter"></i
            ></a>
            <a href="http://pinterest.com/edamam"
              ><i class="fa fa-pinterest-p"></i
            ></a>
          </div>
        </div>
      </div>
    </footer>
</template>

<script>
export default {
  name: "Footer",
}
</script>

<style scoped>
footer {
  left: 0;
  bottom: 0;
  width: 100%;
}

.information-footer {
  text-align: left;
}

.sosmed a {
  font-size: 25px;
  color: white;
  padding-right: 10px;
  padding-left: 10px;
}

.sosmed a:hover {
  color: #f16765;
}
</style>