<template>
<div id="app">
  <a-layout id="components-layout-demo-custom-trigger">
    <a-layout-sider v-model="collapsed" :trigger="null" collapsible>
      <div class="logo" />
        <a-menu theme="dark" mode="inline" :default-selected-keys="['1']">
          <a-menu-item key="1">
            <a-icon type="home" />
            <span>Página Principal</span>
          </a-menu-item>
          <a-menu-item key="2">
            <a-icon type="user" />
            <span>Perfil</span>
          </a-menu-item>
          <a-menu-item key="3">
            <a-icon type="setting" />
            <span>Config.</span>
          </a-menu-item>
        </a-menu>
    </a-layout-sider>
  <a-layout>
    <a-layout-header style="background: #fff; padding: 0">
      <a-icon
        class="trigger"
        :type="collapsed ? 'menu-unfold' : 'menu-fold'"
        @click="() => (collapsed = !collapsed)"
      />
      Dashboard
    </a-layout-header>
    <div class="card-info">
      <div class="card">
        <div class="icon">
          <img src="src\assets\visits.svg" alt="Visitas">
        </div>
        <div class="info">
          <p>Novas Visitas</p>
          <span>102.400</span>
        </div>
      </div>
      <div class="card">
        <div class="icon">
          <img src=".\assets\messages.png" alt="Visitas">
        </div>
        <div class="info">
          <p>Mensagens</p>
          <span>81.212</span>
        </div>
      </div>
      <div class="card">
        <div class="icon">
          ìcone
        </div>
        <div class="info">
          <p>Compras</p>
          <span>9.280</span>
        </div>
      </div>
      <div class="card">
        <div class="icon">
          ìcone
        </div>
        <div class="info">
          <p>Vendas</p>
          <span>13.600</span>
        </div>
      </div>
    </div>
    <a-layout-content
      :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">
    </a-layout-content>
     <line-chart :chartdata="chartData" :options="chartOptions" />
    <div class="card-chart">
      <div class="card">
        <div class="chart">
          ìcone
        </div>
      </div>
      <div class="card">
        <div class="chart">
          ìcone
        </div>
      </div>
      <div class="card">
        <div class="chart">
          ìcone
        </div>
      </div>
    </div>
  </a-layout>
  </a-layout>
  </div>
</template>

<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  props: {
    chartdata: {
      type: Object,
      default: null
    },
    options: {
      type: Object,
      default: null
    }
  },
  mounted() {
    this.renderChart(this.chartdata, this.options);
  }
};

</script>

<style>
.small {
  max-width: 600px;
  margin: 150px auto;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#components-layout-demo-custom-trigger .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

#components-layout-demo-custom-trigger .trigger:hover {
  color: #1890ff;
}

.card-info {
  display: flex;
  padding: 11px;
}

.card {
  display: flex;
  justify-content: space-between;
  background: #fff;
  width: 300px;
  margin: 5px;
  padding: 20px;
}

.card p {
  font-weight: 400;
  color: #27303b;
}

.card span {
  font-size: 18px;
  font-weight: 600;
}

.card-chart {
  display: flex;
  padding: 11px;
}

.card-chart .card {
  display: flex;
  justify-content: space-between;
  background: #fff;
  width: 400px;
  height: 300px;
  margin: 5px;
  padding: 20px;
}

</style>
