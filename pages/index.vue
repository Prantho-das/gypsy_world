<template>
  <section id="sidebar" class="sidebar_nav_small">
    <nav id="sidebar_nav" class="mt-0">
      <nuxt-link to="/" class="active d-flex">
        <i class="text-secondary fa fa-house-chimney d-flex"></i>
        <span>Home</span>
      </nuxt-link>
      <nuxt-link to="/">
        <div class="mt-4">
          <i class="text-secondary fas fa-users"></i>
          <!-- <span>Home</span> -->
        </div>
      </nuxt-link>
      <nuxt-link to="/">
        <div class="mt-4">
          <i class="text-secondary fas fa-video"></i>
          <!-- <span>Home</span> -->
        </div>
      </nuxt-link>
      <nuxt-link to="/">
        <div class="mt-4">
          <i class="text-secondary fa-solid fa-dharmachakra"></i>
          <!-- <span>Home</span> -->
        </div> </nuxt-link
      ><nuxt-link to="/">
        <div class="mt-4">
          <i class="text-secondary fa-solid fa-gift"></i>
          <!-- <span>Home</span> -->
        </div>
      </nuxt-link>
      <nuxt-link to="/">
        <div class="mt-4">
          <i class="text-secondary fa-solid fa-door-closed"></i>
          <!-- <span>Home</span> -->
        </div>
      </nuxt-link>
    </nav>
    <!-- <main>
      <div class="col-10 ml-auto py-3 px-4">
        <h3>Good Morning, John Doe</h3>
        <section id="revenue" class="mt-4">
          <div class="row">
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
          <div class="row">
            <UserCard :title="'Most Active'" :users="users" />
            <UserCard :title="'Top Diamond'" :users="users" />
            <UserCard :title="'Top Level'" :users="users" />
            <UserCard :title="'Top Bean'" :users="users" />
          </div>
        </section>
      </div>
    </main> -->
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
<style>
/* .card{
  box-shadow: 7px 7px 11px 0px rgba(222,222,222,0.75);
-webkit-box-shadow: 7px 7px 11px 0px rgba(222,222,222,0.75);
-moz-box-shadow: 7px 7px 11px 0px rgba(222,222,222,0.75);
} */
</style>
