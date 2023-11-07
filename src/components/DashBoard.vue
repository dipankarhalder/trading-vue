<script setup>
import { dashboardlistitems, tableheader, tablebody } from './utility/content' 
</script>

<template>
  <div class="app_dashboard">
    <div class="app_dashboard_header">

    </div>
    <div class="app_dashboard_body">
      <div class="app_dashboard_body_left">
        <ul class="app_dashboard_head_link">
          <li v-for="item in dashboardlistitems" :key="item.name">
            {{item.name}}
          </li>
        </ul>
        <div class="app_dashboard_table">
          <div class="app_dash_table_header">
            <ul>
              <li v-for="item in tableheader" :key="item">
                {{item}}
              </li>
            </ul>
            <div class="app_dash_table_body">
              <ul class="app_dash_table_list">
                <li v-for="item in tablebody" :key="item.exchange">
                  <p>{{item.exchange}}</p>
                  <p>{{item.symbol}}</p>
                  <p>{{item.name}}</p>
                  <p>{{item.change1}}</p>
                  <p>{{item.change2}}</p>
                  <p>{{item.buy}}</p>
                  <p>{{item.sell}}</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="app_dashboard_body_right"></div>
    </div>
  </div>
</template>

<style scoped>
.app_dashboard {
  display: flex;
  width: calc(100% - 260px);
  height: 100vh;
  flex-direction: column;
  border-left: 1px solid var(--vt-c-text-dark-2);
}
.app_dashboard_header{
  height: 50px;
  border-bottom: 1px solid var(--vt-c-text-dark-2);
}
.app_dashboard_body{
  display: flex;
}
.app_dashboard_body_left,
.app_dashboard_body_right{
  height: calc(100vh - 50px);
}
.app_dashboard_body_left{
  display: flex;
  flex-direction: column;
  width: calc(100% - 380px);
}
.app_dashboard_body_right{
  width: 380px;
  border-left: 1px solid var(--vt-c-text-dark-2);
}
.app_dashboard_head_link{
  display: flex;
  padding: 10px 20px;
  border-bottom: 1px solid var(--vt-c-text-dark-2);
}
.app_dashboard_head_link li{
  text-transform: uppercase;
  font-size: 11px;
  font-weight: 700;
  color: var(--vt-c-indigo);
  margin-right: 8px;
  padding: 4px 12px;
  border-radius: 3px;
  background: var(--vt-c-text-dark-2);
}
.app_dashboard_table{
  display: flex;
  flex-direction: column;
}
.app_dash_table_header ul {
  display: flex;
  padding-left: 0px;
  justify-content: space-between;
}
.app_dash_table_body ul.app_dash_table_list{
  display: flex;
  flex-direction: column;
}
.app_dash_table_list li{
  display: flex;
  justify-content: space-between;
}
</style>
