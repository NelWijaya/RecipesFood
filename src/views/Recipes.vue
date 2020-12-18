<template>
  <div class="recipes mt-5 pt-5">
    <div class="container">
      <div class="row title mb-3">
        <div class="col-12">
          <h3>Search Recipes</h3>
        </div>
      </div>
      <div class="row">
        <div class="col-12">
          <div class="boxContainer">
            <table class="elementsContainer">
              <tr>
                <td>
                  <input
                    type="text"
                    placeholder="Search"
                    class="search"
                    v-model="searchKey"
                  />
                </td>
                <td>
                  <a @click.prevent="searchRecipes"
                    ><i class="material-icons">search</i></a
                  >
                </td>
              </tr>
            </table>
          </div>
        </div>
      </div>
      <section>
        <div v-for="detail in detail" :key="detail.recipe" class="mb-3">
          <div v-if="detail">
            <div class="row my-5">
              <div class="col-12 col-md-5">
                <img :src="detail.image" class="img-fluid mb-5" />
                <br />
                <a :href="detail.url" target="blank" class="btn btn-primary">Step-by-step recipes</a><br><br>
                <a :href="detail.shareAs" target="blank" class="btn btn-primary">Nutritional value</a>
                <br />
                <div class="mt-5">
                  <label class="switch">
                    <input
                      id="myCheck"
                      v-on:click="berubahData"
                      type="checkbox"
                    />
                    <span class="slider round"></span>
                  </label>
                  <h5>Recipes with picture</h5>
                </div>
              </div>
              <div class="col-12 col-md-7">
                <h3>{{ detail.label }}</h3>
                <hr />
                <h5 class="mb-5">Ingredients needed</h5>
                <div id="benar">
                  <ul
                    v-for="list in isiBahan"
                    :key="list.ingredient"
                    style="text-align: left"
                  >
                    <li>{{ list }}</li>
                  </ul>
                  <hr>
                </div>

                <div id="salah">
                  <ul
                    v-for="listG in isiBahanGambar"
                    :key="listG.ingredient"
                    style="text-align: left"
                  >
                    <li>
                      <img :src="listG.image" width="80" /> {{ listG.text }}
                    </li>
                  </ul>
                  <hr>
                </div>
              </div>
            </div>
          </div>
          <div v-else class="apa"></div>
        </div>
      </section>
      <section>
        <div class="row mb-5 mt-5 pt-5">
          <div
            v-for="recipeList in recipeList"
            :key="recipeList.recipes"
            class="col-12 col-sm-6 col-md-4 col-lg-3 mb-3"
          >
            <div class="card">
              <img :src="recipeList.recipe.image" class="card-img-top" />
              <div class="card-body">
                <h5 class="card-title">{{ recipeList.recipe.label }}</h5>
                <p class="card-text">
                  Calories : {{ recipeList.recipe.calories.toFixed(0) }} <br />
                </p>
                <a
                  class="btn btn-primary"
                  @click.prevent="detailRecipe(recipeList)"
                  >Check ingredient</a
                >
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "List",
  props: ["recipes"],
  data() {
    return {
      searchKey: "",
      recipeList: [],
      detail: [],
      isiBahan: [],
      isiBahanGambar: [],
    };
  },
  methods: {
    searchRecipes() {
      axios
        .get(
          "https://api.edamam.com/search?q=" +
            this.searchKey +
            "&app_id=cfe334bb&app_key=9bdacd637856379f6fc33e295cbc2b68"
        )
        .then((response) => {
          this.recipeList = response.data.hits;
          console.log(this.recipeList);
        })
        .catch((error) => {
          console.log("Error", error);
        });
    },

    detailRecipe(newData) {
      this.detail = newData;
      this.isiBahan = newData.recipe.ingredientLines;
      this.isiBahanGambar = newData.recipe.ingredients;
      console.log(this.detail);
    },

    berubahData() {
      var checkBox = document.getElementById("myCheck");
      var benar = document.getElementById("benar");
      var salah = document.getElementById("salah");

      // If the checkbox is checked, display the output text
      if (checkBox.checked == false) {
        benar.style.display = "block";
        salah.style.display = "none";
        
      } else {
        benar.style.display = "none";
        salah.style.display = "block";
      }
    },
  },
};
</script>

<style scoped>
.title {
  text-align: center;
}

.boxContainer {
  margin: auto;
  position: relative;
  width: 300px;
  height: 42px;
  border: 4px solid #f16765;
  padding: 0px 10px;
  border-radius: 50px;
}

.elementsContainer {
  width: 100%;
  height: 100%;
  vertical-align: middle;
}

.elementsContainer a {
  cursor: pointer;
}

.search {
  border: none;
  height: 100%;
  width: 100%;
  padding: 0px 5px;
  border-radius: 50px;
  font-size: 18px;
  font-family: "Nunito";
  color: #f16765;
  font-weight: 500;
}

.search:focus {
  outline: none;
}

.material-icons {
  font-size: 26px;
  color: #f16765;
}

.recipes {
  min-height: 400px;
}
.apa {
  display: none;
}

/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #f16765;
}

input:focus + .slider {
  box-shadow: 0 0 1px #f16765;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

#salah{
  display: none;
}
</style>