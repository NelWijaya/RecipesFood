<template>
  <div class="hello">
      <section>
          <div>{{recipes}}</div>
      </section>
  </div>
</template>

<script>
export default {
  name: "List",
  props:['recipes'],
  data() {
    return {
        searchKey: '',
        recipeList:[],
    };
  },
  methods:{
      searchRecipes(){
          var url='https://api.edamam.com/search?q='+this.searchKey+'&app_id=cfe334bb&app_key=9bdacd637856379f6fc33e295cbc2b68';
          fetch(url)
          .then(response=>response.json())
          .then(data=>{
              this.recipeList=data;
          })
      }
  }
};
</script>

<style scoped>
</style>
