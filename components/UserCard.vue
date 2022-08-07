<template>
  <div class="col-lg-3 col-md-6 col-12">
    <div class="card">
      <div class="card-body">
        <div class="h5">{{ title }}</div>
        <div
          class="d-flex align-items-center gap-3 mt-4"
          v-for="(user, i) in users"
          :key="i"
        >
          <div class="avatar avatar-sm mr-2">
            <img
              :src="user.avatar"
              class="img-fluid rounded-circle"
              alt="..."
              v-if="user.avatar"
            />
            <img
              :src="`https://ui-avatars.com/api/?name=${user.name}`"
              class="img-fluid rounded-circle"
              alt="..."
              v-else
            />
          </div>
          <div>
            <h5 class="mb-0">{{ user.name }}</h5>
            <p class="mb-0 text-secondary">{{ user.desc }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Most Active",
    },
    users: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  overflow-clip-box: content-box;
}
</style>
