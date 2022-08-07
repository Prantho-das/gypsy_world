<template>
  <section>
    <section
      id="sidebar"
      :class="navOpen ? 'sidebar_nav_big' : 'sidebar_nav_small'"
    >
      <div class="logo w-100 text-center">
        <i class="fa-solid fa-circle-notch display-4"></i>
      </div>
      <nav id="sidebar_nav" class="text-center">
        <nuxt-link to="/" class="mt-4">
          <div>
            <i class="text-secondary fa fa-house-chimney"></i>
            <span class="nav-text">Home</span>
          </div>
        </nuxt-link>
        <nuxt-link to="/user">
          <div class="mt-md-4 mt-2">
            <i class="text-secondary fas fa-users"></i>
            <span class="nav-text">User</span>
          </div>
        </nuxt-link>
        <nuxt-link to="/video">
          <div class="mt-md-4 mt-2">
            <i class="text-secondary fas fa-video"></i>
            <span class="nav-text">Video</span>
          </div>
        </nuxt-link>
        <nuxt-link to="/chakra">
          <div class="mt-md-4 mt-2">
            <i class="text-secondary fa-solid fa-dharmachakra"></i>
            <span class="nav-text">Chakra</span>
          </div> </nuxt-link
        ><nuxt-link to="/gift">
          <div class="mt-md-4 mt-2">
            <i class="text-secondary fa-solid fa-gift"></i>
            <span class="nav-text">Gift</span>
          </div>
        </nuxt-link>
        <nuxt-link to="/way">
          <div class="mt-md-4 mt-2">
            <i class="text-secondary fa-solid fa-door-closed"></i>
            <span class="nav-text">Ways</span>
          </div>
        </nuxt-link>
        <i
          class="nav-toggler text-secondary fa-solid fa-bars mt-4 cursor-pointer"
          @click="navOpen = !navOpen"
        ></i>
      </nav>
      <div
        class="user-notify text-center mt-5 d-flex flex-column align-items-center gap-4"
      >
        <nuxt-link to="/notification" class="mt-4">
          <i class="fa-regular fa-bell"></i>
        </nuxt-link>
        <nuxt-link to="/profile" class="avatar">
          <img
            src="https://ui-avatars.com/api/?name=prantho"
            alt=""
            class="img-fluid rounded-circle"
          />
        </nuxt-link>
      </div>
    </section>
    <main>
      <Nuxt />
    </main>
  </section>
</template>
<script>
import TotalCard from "../components/TotalCard.vue";
import UserCard from "../components/UserCard.vue";
import GraphCard from "../components/GraphCard.vue";
export default {
  components: { TotalCard, UserCard, GraphCard },
};
</script>
