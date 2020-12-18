<template>
  <div class="hello">
    <section>
      <div class="container">
        <div class="row mb-3 mt-5">
          <div class="mr-auto">
            <h3>Aneka Resep Pizza</h3>
          </div>
        </div>
        <div class="row mb-5">
          <div
            v-for="pizza in pizza.slice(0, 4)"
            :key="pizza.recipes"
            class="col-12 col-sm-6 col-md-4 col-lg-3 mb-3"
          >
            <div class="card">
              <img :src="pizza.recipe.image" class="card-img-top" />
              <div class="card-body">
                <h5 class="card-title">{{ pizza.recipe.label }}</h5>
                <p class="card-text">
                  Calories : {{ pizza.recipe.calories.toFixed(0) }} <br />
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Pizza",

  data() {
    return {
      pizza:[],
    };
  },
  mounted() {
    axios
      .get(
        "https://api.edamam.com/search?q=pizza&app_id=cfe334bb&app_key=9bdacd637856379f6fc33e295cbc2b68"
      )
      .then((response) => {
        this.pizza = response.data.hits;
        console.log(this.pizza);
      })
      .catch((error) => {
        console.log("Error", error);
      });
  },

};
</script>

<style scoped>
</style>
