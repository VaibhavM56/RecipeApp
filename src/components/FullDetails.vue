<template>
  <div class="main" style="width: 50rem" v-if="show">
    <div class="card mb-3">
      <div class="card-header">
        <h2>{{ name }}</h2>
      </div>
      <img :src="img" class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">
          <strong>Steps in making {{ name }}</strong>
        </h5>
        <p class="card-text">
          {{ description }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
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
    show: {
      required: true,
    },
  },
};
</script>

<style scoped>
h2 {
  font-weight: bold;
}
.main {
  margin-left: 20%;
}
</style>
