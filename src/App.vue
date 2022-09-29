<template>
  <h1>Recipe Book</h1>
  <div class="flex-box">
    <div>
      <recipe-details
        v-for="recipe in recipes"
        :key="recipe.id"
        :name="recipe.name"
        :description="recipe.description"
        :id="recipe.id"
        :img="recipe.img"
        @toggleRecipeStatus="toggleRecipeStatus"
      />
    </div>
    <div>
      <full-details
        v-for="recipe in recipes"
        :key="recipe.id"
        :name="recipe.name"
        :description="recipe.description"
        :id="recipe.id"
        :img="recipe.img"
        :show="recipe.showRecipe"
      />
    </div>
  </div>
</template>

<script>
import RecipeDetails from "./components/RecipeDetails.vue";
import FullDetails from "./components/FullDetails.vue";
export default {
  name: "App",
  components: { RecipeDetails, FullDetails },
  data() {
    return {
      recipes: [
        {
          id: "1",
          name: "Gulab Jamun",
          img: "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2020/11/06/FNK_Gulab-Jamun_H1.jpg.rend.hgtvcom.826.620.suffix/1604695335894.jpeg",
          description:
            "Boil sugar and water to prepare syrup remove from fire; add cardamom and keep aside to cool.In a mixing bowl put the flour, paneer, sooji, Nestlé MILKMAID , baking powder and baking soda. Mix gently to make a soft dough, do not knead too much.Divide the mixture into 30-35 portions and gently roll into round gulab jamuns. Fry in the oil at very low flame till golden brown in color.Keep putting the fried gulab jamuns in the prepared sugar syrup, once all the gulab jamuns are in the sugar syrup bring it to a boil and remove from flame.Serve warm.",
          showRecipe: false,
        },
        {
          id: "2",
          name: "Rasmalai",
          img: "https://media.istockphoto.com/photos/traditional-rasmalai-or-ras-malai-indian-dessert-bengali-sweet-picture-id515853026?k=20&m=515853026&s=612x612&w=0&h=Gl2K9s6bxCibj8a99hMldwwmP9fHSud3d6fNcl6yPao=",
          description:
            "Further mash paneer with hand for at least 6 minutes to make smooth dough.Alongside take a pan add sugar and water together and bring to boil to make syrup for cooking rasmalai.Make small balls of paneer dough and flatten, add into boiling sugar syrup, cover and cook for 10 minutes on medium heat. Remove and keep aside to cool.In another pan pour in the Nestlé a+ milk and Nestlé MILKMAID, bring to boil and reduce to half. Turn of the flame, add saffron and cardamom powder and mix well. Allow to cool.Take out the Rasgullas from sugar syrup squeeze gently to remove the sugar syrup and put them into saffron ras,Garnished with chopped pistachio and serve chilled.",
          showRecipe: false,
        },
        {
          id: "3",
          name: "Gajar Ka Halwa",
          img: "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2020/11/06/FNK_Gajar-Ka-Halwa_H1.jpg.rend.hgtvcom.826.620.suffix/1604695300535.jpeg",
          description:
            "Mix carrots and milk in a pan, bring to a boil. Cook on low flame, stirring occasionally, until milk dries up.Add Nestlé MILKMAID and continue cooking on low flame, stirring occasionally, until it dries up.Add ghee and cook for another 10 minutes. Garnish your gajar ka halwa with cashewnuts and raisins, and serve hot.",
          showRecipe: false,
        },
      ],
    };
  },
  methods: {
    // getUserShowRecipe(showRecipe) {
    //   this.userShowRecipe = showRecipe;
    toggleRecipeStatus(recipeID) {
      let identifiedRecipe = this.recipes.find(
        (recipe) => recipe.id === recipeID
      );
      identifiedRecipe.showRecipe = !identifiedRecipe.showRecipe;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

h1 {
  background-color: #1d9819;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
  padding: 10px 20px;
  color: white;
  box-shadow: 1px 4px lightgrey;
}

.flex-box {
  display: flex;
}
</style>
