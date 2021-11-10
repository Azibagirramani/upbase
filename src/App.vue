<template>
  <div id="App" class="row flex-nowrap vh-100 w-100">
    <div
      class="
        col-auto col-md-3 col-xl-2 col-sm-1
        sticky-top
        px-sm-2 px-0
        d-flex
        justify-content-center
        align-items-sm-start
        min-vh-100
      "
    >
      <div ref="sideNav">
        <SideBar />
      </div>
    </div>
    <!-- main content section -->
    <div class="col p-0">
      <div class="b-g-grey border-l-b-curve content-height">
        <!-- dashboard top navigation -->
        <div
          class="
            d-flex
            justify-content-end
            gap-5
            align-items-center
            stock
            py-4
            pe-5
          "
        >
          <div class="d-flex gap-2 align-items-center">
            <i class="fa fa-sun-o light-grey" aria-hidden="true"></i>
            <p class="m-0 p-0 light-grey">US Stocks market opens in 3 hours</p>
          </div>
          <div class="d-flex gap-3 align-items-center wallet">
            <p class="m-0 p-0 text-dark fs-1-3">Main Wallet</p>
            <i class="fa fa-sort-desc mb-1" aria-hidden="true"></i>
          </div>
          <i class="fa fa-bell-o" aria-hidden="true"></i>
          <button class="btn btn-dark circle">
            <i class="fa fa-plus text-white" aria-hidden="true"></i>
          </button>
        </div>
        <!-- end of dashboard top navigation -->

        <!-- dashboard top stock highlight -->
        <div class="container px-5 d-flex justify-content-end">
          <div class="row gx-4 gy-4 w-100 transform-translate">
            <div class="col-md-4 d-flex">
              <CardBase>
                <div>
                  <h5 class="text-center my-3 p-0">Upgrade your Account</h5>
                  <div class="row">
                    <div class="col-md-6 d-none d-lg-block">
                      <img
                        src="./assets/portrait.svg"
                        class="upgrade-account-image mt-4"
                      />
                    </div>
                    <div class="col-md-6 col-sm-12">
                      <p class="font-1-1">
                        Access many other features and helpful insight
                      </p>
                      <div class="d-flex justify-content-end">
                        <button class="btn btn-dark btn-lg mt-4 rounded-3">
                          <i class="fa fa-arrow-right" aria-hidden="true"></i>
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </CardBase>
            </div>
            <div class="col-md-8 d-flex">
              <CardBase>
                <div>
                  <div class="d-flex justify-content-between">
                    <nav class="nav">
                      <a class="nav-link" href="#/">1d</a>
                      <a class="nav-link" href="#/">1w</a>
                      <a class="nav-link" href="#/">1m</a>
                      <a class="nav-link" href="#/">1y</a>
                      <a class="nav-link" href="#/">All</a>
                    </nav>
                    <i class="fa fa-usd" aria-hidden="true"></i>
                  </div>
                  <div class="row">
                    <!-- lin chart here -->
                    <div class="col-md-8 py-0 m-0 fixed-width">
                      <Chart
                        :options="barConfig.options"
                        :series="barConfig.series"
                      />
                    </div>
                    <div
                      class="col-md-4 d-flex flex-row flex-lg-column mt-lg-4"
                    >
                      <div>
                        <h6 class="m-0">Profolio Value</h6>
                        <h3>$ 9 864.34</h3>
                        <div
                          class="d-flex align-content-center gap-2 text-success"
                        >
                          <i
                            class="fs-1-3 fa fa-arrow-up"
                            aria-hidden="true"
                          ></i>
                          <h6 class="fs-1-3 fw-700">234 23 (30.34%)</h6>
                        </div>
                      </div>
                      <div class="mt-lg-4">
                        <nav class="nav legend flex-column">
                          <a class="nav-link" href="#">
                            <i
                              class="fa fa-stop legend-first"
                              aria-hidden="true"
                            ></i>
                            <span class="ps-2">Profolio</span></a
                          >
                          <a class="nav-link" href="#">
                            <i
                              class="fa fa-stop legend-second"
                              aria-hidden="true"
                            ></i
                            ><span class="ps-2">Dollar</span></a
                          >
                          <a class="nav-link" href="#">
                            <i
                              class="fa fa-stop legend-third"
                              aria-hidden="true"
                            ></i
                            ><span class="ps-2">ETFs</span></a
                          >
                        </nav>
                      </div>
                    </div>
                  </div>
                </div>
              </CardBase>
            </div>
          </div>
        </div>
        <!-- end of dashboard top stock highlight -->
      </div>

      <div class="content-maring-top">
        <!-- portfolio section -->
        <div class="mt-lg-5 mt-2 px-5">
          <div class="ps-4">
            <div class="d-flex justify-content-between">
              <p class="text-dark fw-600">Profolio History</p>
              <p class="text-dark text-underlin-dot">Per Industry</p>
            </div>
            <div class="row w-100 gy-4">
              <div class="col-md-8">
                <div class="row col-cols-1 g-4 row-cols-lg-3">
                  <div
                    class="col d-flex"
                    v-for="(counter, index) in [1, 2, 4]"
                    :key="index"
                  >
                    <CardBase
                      :bordered="true"
                      :custom="index === 1 ? 'border card-bg-grey' : 'border'"
                    >
                      <div
                        class="
                          pofolio-history
                          d-flex
                          flex-column
                          justify-content-end
                        "
                      >
                        <h5>NOV 19</h5>
                        <Chart
                          v-if="index === 1"
                          :options="lineConfig.options"
                          :series="lineConfig.series"
                        />
                        <div class="mt-auto">
                          <h6 class="m-0">Profolio Value</h6>
                          <h3 :class="indexx === 2 ? 'text-danger' : ''">
                            $ 9 864.34
                          </h3>
                          <div
                            class="
                              d-flex
                              align-content-center
                              gap-2
                              text-success
                            "
                          >
                            <i
                              class="fs-1-3 fa"
                              :class="
                                index === 2 ? 'fa-arrow-down' : 'fa-arrow-up'
                              "
                              aria-hidden="true"
                            ></i>
                            <h6 class="fs-1-3 fw-700">234 23 (30.34%)</h6>
                          </div>
                        </div>
                      </div>
                    </CardBase>
                  </div>
                </div>
              </div>
              <div class="col-md-4 d-flex">
                <CardBase :bordered="true" :custom="'card-bg-primary'">
                  <div class="d-flex justify-content-end">
                    <i
                      class="fa fa-tachometer text-white"
                      aria-hidden="true"
                    ></i>
                  </div>
                  <div class="d-flex flex-column align-items-center">
                    <Chart
                      :options="donutConfig.options"
                      :series="donutConfig.series"
                    />
                  </div>
                </CardBase>
              </div>
            </div>
          </div>
        </div>
        <!-- end portfolio section -->

        <!-- stats section -->
        <div class="px-5">
          <div class="ps-4">
            <div
              class="
                d-flex
                gap-5
                my-5
                flex-column flex-lg-row
                justify-content-between
              "
            >
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 text-lg-end fw-700">
                  SYMBOLS
                </p>
                <div
                  class="
                    d-flex
                    symbols
                    align-items-center
                    justify-content-lg-center
                  "
                >
                  <img
                    src="./assets/applelogo.png"
                    width="30"
                    class="img-fluid ms-2 ms-lg-4 me-lg-3 me-2 rounded-100"
                    alt="applelogo"
                  />
                  <p class="mt-2 fw-bold">APPL</p>
                </div>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 text-lg-end fw-700">
                  PRICE
                </p>
                <p class="mt-2 fw-600">= $ 234.00</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">% RETURN</p>
                <p class="mt-2 text-success fw-600">$ 45.43</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">TOTAL NET COST</p>
                <p class="mt-2 fw-600">$ 1234.00</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">MARKET VALUE</p>
                <p class="mt-2 fw-600">$ 1345.87</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">TOTAL GAIN</p>
                <p class="mt-2 text-success fw-600">$ 456.34</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">DAILY GAIN</p>
                <p class="mt-2 text-danger fw-600">-$ 3.45</p>
              </div>
              <div class="d-flex flex-column">
                <p class="light-grey m-0 p-0 fs-1-2 fw-700">% PORFOLIO</p>
                <p class="mt-2 fw-600">13,45%</p>
              </div>
            </div>
          </div>
        </div>
        <!-- end of stats section -->
      </div>
    </div>
    <!-- main content section -->
  </div>
</template>

<script lang="ts">
import SideBar from "./components/SideBar.vue";
import CardBase from "./components/CardBase.vue";
import Chart from "./components/Chart.vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    CardBase,
    Chart,
  },
  methods: {
    showNav() {
      (this.$refs["sideNav"] as any).style.marginLeft = "0px";
    },
  },
  data() {
    return {
      donutConfig: {
        series: [44, 55, 41, 17, 15],
        options: {
          legend: false,
          dataLabels: {
            enabled: false,
          },
          chart: {
            type: "donut",
            size: 2,
            labels: {
              show: true,
              name: {
                show: true,
                text: "07",
              },
              value: {},
            },
          },
        },
      },
      lineConfig: {
        series: [
          {
            data: [10, 41, 35, 51, 49, 62, 69, 91, 148],
          },
        ],
        options: {
          chart: {
            toolbar: {
              show: false,
            },
            type: "line",
            zoom: {
              enabled: false,
            },
            background: "transparent",
          },
          legend: {
            enabled: false,
          },
          dataLabels: {
            enabled: false,
          },
          stroke: {
            curve: "straight",
          },
          title: {
            enabled: false,
          },
          grid: {
            show: false, // you can either change hear to disable all grids
            xaxis: {
              lines: {
                show: false, //or just here to disable only x axis grids
              },
            },
            yaxis: {
              lines: {
                show: false, //or just here to disable only y axis
              },
            },
          },
          tooltip: {
            enabled: false,
          },
          xaxis: {
            labels: {
              show: false,
            },
            axisTicks: {
              show: false,
            },
            axisBorder: {
              show: false,
            },
            lines: {
              show: false,
            },
          },
          yaxis: {
            labels: {
              show: false,
            },
            lines: {
              show: false,
            },
          },
        },
      },
      barConfig: {
        options: {
          legend: {
            show: false,
          },
          chart: {
            type: "bar",
            width: "20%",
            stacked: true,
            toolbar: {
              show: false,
            },
          },
          plotOptions: {
            bar: {
              columnWidth: 20,
              barHeight: "10%",
            },
          },
          noData: {
            text: "No data",
            align: "center",
            verticalAlign: "middle",
            offsetX: 0,
            offsetY: 0,
            style: {
              color: "Red",
              fontSize: "14px",
            },
          },
          grid: {
            show: false,
          },
          yaxis: {
            labels: {
              show: false,
            },
            axisTicks: {
              show: false,
            },
            axisBorder: {
              show: false,
            },
            lines: {
              show: false,
            },
          },
          xaxis: {
            type: "category",
            categories: [
              "Jan",
              "Feb",
              "Mar",
              "Apr",
              "May",
              "Jun",
              "jul",
              "Aug",
              "Sep",
              "Oct",
              "Nov",
              "Dec",
            ],
            labels: {
              show: true,
              rotateAlways: false,
              rotate: 0,
              style: {
                fontSize: "0.5rem",
                cssClass: "bar-chart-css",
              },
            },
            axisTicks: {
              show: false,
            },
            axisBorder: {
              show: false,
            },
            lines: {
              show: false,
            },
          },
          dataLabels: {
            enabled: false,
          },
          tooltip: {
            enabled: false,
          },
        },
        series: [
          {
            data: [44, 55, 41, 17, 15, 22, 56, 31, 44, 55, 41, 17],
          },
          {
            data: [44, 55, 41, 17, 15, 22, 56, 31, 44, 55, 41, 17],
          },
          {
            data: [44, 55, 41, 17, 15, 22, 56, 31, 44, 55, 41, 17],
          },
        ],
      },
    };
  },
});
</script>

<style lang="scss" scoped>
$legend-first-color: #0524f7;
$legend-second-color: #8ccfee;
$legend-third-color: #f75354;

.content-maring-top {
  margin-top: 9rem;
}

.content-height {
  height: 16rem;
}

.fixed-width {
  position: relative;
  width: 60%;
}

.main {
  margin-left: 0% !important;
}

.sidebar {
  height: 100%; /* Full-height: remove this if you want "auto" height */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  z-index: 1; /* Stay on top */
  top: 0; /* Stay at the top */
  left: 0;
  width: 18rem !important;
  overflow-x: hidden; /* Disable horizontal scroll */
}

/* Style page content */
.main-content {
  margin-left: 18rem; /* Same as the width of the sidebar */
  padding: 0px 10px;
}

@media only screen and (max-width: 799px) {
  .sidebar {
    display: none !important;
  }

  .main-content {
    margin-left: 0rem; /* Same as the width of the sidebar */
  }
}

.upgrade-account-image {
  transform: translate(-30%, 50%);
  transform: scale(2.1);
  width: 100% !important;
  transition: transform 0.5s ease-in-out;
}

.symbols {
  border-left: 3px solid #aad7ea;
}

.rounded-100 {
  border-radius: 100%;
}

.text-underlin-dot {
  text-decoration: underline dotted black 3px !important;
  font-size: 0.75rem;
  font-weight: 700;
}

.second-section {
  margin-top: 8rem;
}

.ch-30 {
  height: 17rem;
}

.fw-600 {
  font-weight: 600;
}

.border-l-b-curve {
  border-radius: 0 0 0 30%;
}

.hightlight-cards {
  transform: translateY(5%);
}

.legend-first {
  color: $legend-first-color;
}

.legend-second {
  color: $legend-second-color;
}

.legend-third {
  color: $legend-third-color;
}

.legend .nav-link:hover {
  color: #a4a4b0 !important;
}

.legend .nav-link {
  padding-left: 0rem;
}

.pofolio-history h5 {
  font-size: 1.2rem;
  font-weight: 700 !important;
}

.pofolio-history h5::after {
  content: "";
  display: block;
  width: 20%;
  margin-top: 0.8rem;
  height: 5px;
  background-color: #a4a4b0;
}

nav .nav-link {
  color: #a4a4b0;
  font-size: 0.7rem;
  font-weight: 700;
  padding: 0.2rem 0.5rem;
  position: relative;
}

nav .nav-link:hover {
  color: black;
}

.font-1-1 {
  font-size: 0.8rem;
  color: #b0aeb7;
  font-weight: 700;
}

.fs-1-2 {
  font-size: 0.62rem !important;
  font-weight: 600;
}
.fs-1-3 {
  font-size: 0.7rem !important;
  font-weight: 600;
}

.wallet i {
  font-size: 0.7rem !important;
  color: #a4a4b0;
}

.stock p {
  font-size: 0.7rem;
}

.fs-1-5 {
  font-size: 1rem !important;
  font-weight: 600;
}
.light-grey {
  color: #a4a4b0;
}

.bg-gray {
  background-color: #eff1f5;
}

.circle {
  border-radius: 100%;
}

.fw-700 {
  font-weight: 700;
}
</style>
