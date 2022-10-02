<template>
  <div class="side" style="width: 18rem" @click="toggleRecipe">
    <div class="card text-center">
      <div class="card-header">
        <strong>{{ id }}</strong>
      </div>
      <div class="card-header">
        <strong>{{ name }}</strong>
      </div>
      <img :src="img" class="card-img-top" alt="..." />
    </div>
  </div>
</template>
<script>
export default {
  emits: ["toggleRecipeStatus"], //(not necessary, used to keep track of function coming from other component)
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    img: {
      required: true,
    },
  },
  // data() {
  //   return {
  //     showRecipe: false,
  //   };
  // },
  methods: {
    toggleRecipe() {
      // this.showRecipe = !this.showRecipe;
      this.$emit("toggleRecipeStatus", this.id);
    },
  },
};
</script>

<style>
.flex-box {
  display: flex;
}

.side {
  flex: 0.2;
  display: flex;
  flex-direction: column;
  margin-left: 5%;
}
</style>
