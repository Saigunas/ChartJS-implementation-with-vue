
<script setup>
  import { ref } from "vue";
  import Home from "./components/Home.vue"
  import Chart from "./components/Chart.vue"

  let activeTab = ref('Home');
</script>
<template>
  <div id="app-body">
    <nav class="navbar navbar-dark bg-dark navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand ps-4" href="#">
        <img src="./assets/chart2.png" alt="Netflix App" />
      </a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <a @click="activeTab = 'Home'" class="nav-item nav-link active" href="#"><i class="bi bi-house-door-fill me-2"></i>Home</a>
          <a @click="activeTab = 'Chart'" class="nav-item nav-link" href="#"><i class="bi bi-bar-chart-line-fill me-2"></i>Chart</a>
          <a @click="activeTab = 'About'" class="nav-item nav-link disabled" href="#"><i class="bi bi-info-circle-fill me-2"></i>About</a>
        </div>
      </div>
    </nav>

    <home v-if="activeTab === 'Home'"/>

    <chart v-if="activeTab === 'Chart'"/>

    <div v-if="activeTab === 'About'">
      About
    </div>

    <footer class="footer bg-dark text-white py-2">
  <div class="container">
    <div class="row">
      <div class="col-md-6 d-flex align-items-center gap-2">
        <a href="https://github.com/Saigunas/Chart-website"><i class="bi bi-github h3 m-0"></i></a>
        <span>University project for data visualization</span>
      </div>
      <div class="col-md-6 d-flex align-items-center justify-content-end">
        <span class="footer-information" style="margin-left: auto">Project was made by Karolis, Gvidas, Saigunas.</span>
      </div>
    </div>
  </div>
</footer>
  </div>
</template>


<style scoped>
#app-body {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 100vh;
}

.navbar-nav a:hover {
  transform: translateY(-5px);
}

.nav-item{
  transition: transform 0.3s ease, border-bottom 0.3s ease;
}

.nav-item:hover{
  transform: translateY(-5px);
}


.navbar-nav a:hover::after {
  content: '';
  display: block;
  height: 2px;
  width: 100%;
  background-color: orangered;
  position: absolute;
  bottom: -5px;
  left: 0;
}

.navbar {
  animation: slideInDown 0.5s ease;
}
</style>
