<template>
  <div class="card">
    <div class="card-body">
      <div class="d-flex flex-md-row flex-column align-items-center justify-content-between">
        <h5>User activity</h5>
        <div class="activity_tab d-flex gap-3">
          <h5
            @click="tab = 'daily'"
            :class="tab === 'daily' ? 'active_tab' : 'text-secondary'"
          >
            Daily
          </h5>
          <h5
            @click="tab = 'weakly'"
            :class="tab === 'weakly' ? 'active_tab' : 'text-secondary'"
          >
            Weakly
          </h5>
          <h5
            @click="tab = 'monthly'"
            :class="tab === 'monthly' ? 'active_tab' : 'text-secondary'"
          >
            Monthly
          </h5>
        </div>
      </div>
      <div class="chart">
        <div class="d-flex flex-md-row flex-column gap-md-5 mt-md-0 mt-2">
          <h1>1730</h1>
          <div class="d-flex align-items-center gap-2">
            <div class="icon py-1 px-2 bg-success rounded-circle mb-3">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                style="width: 18px; height: 18px; margin-bottom: 3px"
                fill="none"
                viewBox="0 0 24 24"
                stroke="white"
                stroke-width="2"
              >
                <path d="M12 14l9-5-9-5-9 5 9 5z" />
                <path
                  d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"
                />
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222"
                />
              </svg>
            </div>
            <div class="text">
              <p class="text-success mb-0">0.8%</p>
              <p class="text-secondary">Than last Day</p>
            </div>
          </div>
        </div>
        <transition name="fade" :duration="500" mode="out-in" appear>
          <div
            class="cartCanvas"
            v-if="tab == 'daily'"
            style="height: 500px; overflow: hidden"
          >
            <canvas id="myChart"></canvas>
          </div>
          <div
            class="cartCanvas"
            v-if="tab == 'weakly'"
            style="height: 500px; overflow: hidden"
          >
            <canvas id="myChart"></canvas>
          </div>
          <div
            class="cartCanvas"
            v-if="tab == 'monthly'"
            style="height: 500px; overflow: hidden"
          >
            <canvas id="myChart"></canvas>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: "monthly",
    };
  },
  mounted() {
    const ctx = document.getElementById("myChart");
    //  ctx.canvas.parentNode.style.height = '128px';
    const myChart = new Chart(ctx, {
      type: "line",
      data: {
        labels: ["Sat", "Sun", "Mon", "Tue", "Wed", "Thu", "Fri"],
        datasets: [
          {
            data: [600, 1400, 1500, 700, 760, 1300, 1500],
            backgroundColor: "black",
            borderColor: "black",
            borderWidth: 2,
          },
        ],
      },
      options: {
        responsive: true,
        scales: {
          y: {
            beginAtZero: true,
            ticks: {
              callback: function (value, index) {
                return "$" + value;
              },
            },
          },
        },
        plugins: {
          legend: {
            display: false, //This will do the task
          },
        },
      },
    });
  },
};
</script>
<style>
.activity_tab h5 {
  position: relative;
  cursor: pointer;
}
.active_tab::before {
  content: "";
  position: absolute;
  bottom: -7px;
  width: 100%;
  height: 3px;
  border-radius: 15%;
  left: 0;
  background-color: black;
  font-weight: 600;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
