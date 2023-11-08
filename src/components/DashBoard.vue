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
              <li>&nbsp;</li>
            </ul>
            <div class="app_dash_table_body">
              <ul class="app_dash_table_list">
                <li v-for="item in tablebody" :key="item.exchange">
                  <p>{{item.exchange}}</p>
                  <p>{{item.symbol}}</p>
                  <p>{{item.name}}</p>
                  <p>{{item.change1}}</p>
                  <p>{{item.change2}}</p>
                  <p class="buy">
                    <span v-if="item.isBuy" class="purchased">{{item.buy}}</span>
                    <span v-else>{{item.buy}}</span>
                  </p>
                  <p class="sell">
                    <span v-if="item.isSell" class="sold">{{item.sell}}</span>
                    <span v-else>{{item.buy}}</span>
                  </p>
                  <p class="action"><span>+</span></p>
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
  padding: 10px 16px;
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
  transition: 0.5s;
  cursor: pointer;
  background: var(--vt-c-text-dark-2);
}
.app_dashboard_head_link li:first-child, 
.app_dashboard_head_link li:hover{
  background: var(--vt-c-indigo);
  color: var(--white);
  transition: 0.5s;
}
.app_dashboard_table{
  display: flex;
  flex-direction: column;
}
.app_dash_table_header > ul {
  display: flex;
  padding-left: 0px;
  justify-content: space-between;
  background: var(--vt-c-text-dark-2);
}
.app_dash_table_header > ul > li {
  padding: 6px 0px;
  font-weight: 700;
}
.app_dash_table_header > ul > li:nth-child(3) {
  width: calc(36% - 40px);
}
.app_dash_table_header > ul > li:nth-child(2),
.app_dash_table_header > ul > li:nth-child(4),
.app_dash_table_header > ul > li:nth-child(5), 
.app_dash_table_header > ul > li:nth-child(6),
.app_dash_table_header > ul > li:nth-child(7) {
  width: 10%;
}
.app_dash_table_header > ul > li:nth-child(8) {
  width: 40px;
}
.app_dash_table_header > ul > li:nth-child(1) {
  width: 14%;
  padding-left: 16px;
}
.app_dash_table_body ul.app_dash_table_list{
  display: flex;
  padding-left: 0px;
  flex-direction: column;
  overflow: auto;
  height: calc(100vh - 130px);
}
.app_dash_table_list > li{
  display: flex;
  padding: 9px 0px;
  justify-content: space-between;
  border-bottom: 1px solid var(--vt-c-text-dark-2);
}
.app_dash_table_list > li p {
  font-size: 14px;
  font-weight: 600;
}
.app_dash_table_list > li > p:nth-child(3) {
  width: calc(36% - 40px);
}
.app_dash_table_list > li > p:nth-child(2),
.app_dash_table_list > li > p:nth-child(4),
.app_dash_table_list > li > p:nth-child(5), 
.app_dash_table_list > li > p:nth-child(6),
.app_dash_table_list > li > p:nth-child(7) {
  width: 10%;
}
.app_dash_table_list > li > p:nth-child(8) {
  width: 40px;
}
.app_dash_table_list > li > p:nth-child(1) {
  width: 14%;
  padding-left: 16px;
}
.app_dash_table_list > li > p.buy > span, 
.app_dash_table_list > li > p.sell > span {
  width: 90%;
  padding: 3px 6px;
  border-radius: 3px;
  font-size: 12px;
  font-weight: 600;
  text-align: right;
  float: left;
  border: 1px solid var(--vt-c-text-light-2);
}
.app_dash_table_list > li > p.buy > span.purchased, 
.app_dash_table_list > li > p.sell > span.sold {
  background: var(--vt-c-text-light-2);
  color: var(--white);
}
.app_dash_table_list > li > p.action > span {
  padding: 3px 9px;
  border-radius: 3px;
  font-size: 12px;
  font-weight: 700;
  text-align: right;
  float: left;
  transition: 0.5s;
  cursor: pointer;
  border: 1px solid var(--vt-c-text-light-2);
}
.app_dash_table_list > li > p.action > span:hover{
  background: var(--vt-c-indigo);
  color: var(--white);
  transition: 0.5s;
}
</style>
