<template>
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
