<template>  <div class="col-lg-3 col-md-6 col-12">
  <div class="card">
    <div class="card-body d-flex align-items-center justify-content-between">
      <div>
        <p class="mb-0 text-secondary">{{ title }}</p>
        <h3 v-html="value"></h3>
      </div>
      <div class="icon rounded py-3 px-3">
        <slot />
      </div>
    </div>
  </div></div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Total revenue",
    },
    value: {
      type: String,
      default: 0,
    },
  },
};
</script>

<style scoped>
.card .icon {
  background-color: #cfe2fc;
}
.icon i{
  color: #94AFD3;
  font-size:20px;
  text-align: center;
}
</style>
