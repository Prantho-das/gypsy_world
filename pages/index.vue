<template>
  <section class="d-flex">
    <div
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
        class="user-notify text-center mt-4 d-flex flex-column align-items-center gap-4"
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
    </div>
    <main>
      <section id="main-content">
        <div :class="navOpen ? 'big_content' : 'small_content'">
          <h3>Good Morning, John Doe</h3>
          <section id="revenue" class="mt-4">
            <div class="row gap-md-0 gap-2">
              <TotalCard title="Total revenue" value="5468.37 &#8364;">
                <i class="fa-solid fa-euro-sign"></i>
              </TotalCard>
              <TotalCard title="Total User" value="5436">
                <i class="fa-regular fa-user"></i>
              </TotalCard>
              <TotalCard title="Active User" value="1730">
                <i class="fa-solid fa-user-check"></i>
              </TotalCard>
              <TotalCard title="Total revenue" value="720">
                <i class="fa-solid fa-video"></i>
              </TotalCard>
            </div>
          </section>
          <section id="graph" class="mt-4">
            <GraphCard />
          </section>
          <section id="user" class="mt-4">
            <div class="row gap-md-0 gap-2">
              <UserCard :title="'Most Active'" :users="users" />
              <UserCard :title="'Top Diamond'" :users="users" />
              <UserCard :title="'Top Level'" :users="users" />
              <UserCard :title="'Top Bean'" :users="users" />
            </div>
          </section>
        </div>
      </section>
    </main>
  </section>
</template>

<script>
import TotalCard from "../components/TotalCard.vue";
import UserCard from "../components/UserCard.vue";
import GraphCard from "../components/GraphCard.vue";
export default {
  name: "IndexPage",
  data() {
    return {
      navOpen: false,
      users: [
        {
          name: "John Doe",
          desc: "18 hrs",
        },
        {
          name: "mika",
          desc: "1 hrs",
        },
        {
          name: "David Doe",
          desc: "2 hrs",
        },
        {
          name: "Hayder Jahid",
          desc: "16 hrs",
        },
        {
          name: "Benny Chagur",
          desc: "18 hrs",
        },
      ],
    };
  },

  components: { TotalCard, UserCard, GraphCard },
};
</script>
