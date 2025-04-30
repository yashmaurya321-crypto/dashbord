
<template>
  <div id="app">
  
    <AppNavbar />
    <div class="main-content">
      
      <RightBar/>
       <LeftBar/>
      
    </div>
  </div>
</template>

<script>
import LeftBar from './LeftBar.vue';
import AppNavbar from './Navbar.vue';
import RightBar from './RightBar.vue';

export default {
  name: 'TurHRDashboard',
  components: {
    AppNavbar,
    RightBar,
    LeftBar
  }
}
</script>

<style>


* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideInRight {
  from { transform: translateX(30px); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}

@keyframes slideInLeft {
  from { transform: translateX(-30px); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}

@keyframes slideInDown {
  from { transform: translateY(-30px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

@keyframes slideInUp {
  from { transform: translateY(30px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

@keyframes scaleIn {
  from { transform: scale(0.9); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}

@keyframes progressLoad {
  from { width: 0; }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
  40% { transform: translateY(-15px); }
  60% { transform: translateY(-7px); }
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

@keyframes barGrow {
  from { height: 0; }
}

body {
  background-color: #f5f5f7;
  color: #333;
  animation: fadeIn 0.8s ease-out;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  display: flex;
  flex: 1;
}

.navbar {
  background-color: white;
  padding: 15px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
  flex-wrap: wrap;
  animation: slideInDown 0.5s ease-out;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  background-color: #7e57c2;
  color: white;
  font-weight: bold;
  padding: 8px 12px;
  border-radius: 8px;
  margin-right: 15px;
  animation: pulse 2s infinite ease-in-out;
}

.page-title {
  font-size: 18px;
  font-weight: 600;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
}

.search-container {
  position: relative;
  animation: slideInRight 0.6s ease-out;
}

.search-input {
  padding: 8px 15px 8px 35px;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  width: 250px;
  transition: box-shadow 0.3s ease;
}

.search-input:focus {
  box-shadow: 0 0 0 2px rgba(126, 87, 194, 0.3);
  outline: none;
}

.search-container.small .search-input {
  width: 180px;
  font-size: 14px;
  padding: 6px 12px 6px 30px;
}

.search-icon {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: #999;
  font-size: 14px;
}

.icon-btn {
  background: none;
  border: none;
  font-size: 18px;
  cursor: pointer;
  color: #666;
  transition: color 0.3s ease, transform 0.3s ease;
  animation: fadeIn 0.7s ease-out;
}

.icon-btn:hover {
  color: #7e57c2;
  transform: scale(1.1);
}

.user-avatars {
  display: flex;
  align-items: center;
  animation: slideInRight 0.7s ease-out;
}

.avatar {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 2px solid white;
  margin-left: -10px;
  transition: transform 0.3s ease;
}

.avatar:hover {
  transform: translateY(-3px);
}

.avatar:first-child {
  margin-left: 0;
}

.user-avatars.small .avatar {
  width: 20px;
  height: 20px;
}

.avatar-count {
  background-color: #e0e0e0;
  color: #666;
  font-size: 12px;
  padding: 2px 6px;
  border-radius: 10px;
  margin-left: 5px;
}

.invite-btn {
  background-color: #f5f5f7;
  color: #333;
  border: none;
  padding: 8px 15px;
  border-radius: 8px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
  animation: slideInRight 0.8s ease-out;
}

.invite-btn:hover {
  background-color: #e6e6ea;
  transform: translateY(-2px);
}

.sidebar {
  width: 300px;
  background-color: white;
  padding: 20px 0;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;
  transition: all 0.3s ease;
  animation: slideInLeft 0.6s ease-out;
}

.sidebar-section {
  margin-bottom: 25px;
  padding: 0 15px;
}

.sidebar-title {
  font-size: 12px;
  color: #999;
  margin-bottom: 10px;
  padding: 0 10px;
}

.sidebar-link {
  display: flex;
  align-items: center;
  padding: 10px;
  color: #666;
  text-decoration: none;
  border-radius: 6px;
  margin-bottom: 2px;
  transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
}

.sidebar-link:hover {
  background-color: #f5f5f7;
  transform: translateX(3px);
}

.sidebar-link.active {
  background-color: #f5f5f7;
  color: #7e57c2;
  font-weight: 500;
}

.sidebar-icon {
  margin-right: 10px;
  font-size: 16px;
}

.announcements {
  margin-top: auto;
  padding: 15px;
  background-color: #f9f9fb;
  margin: 20px 15px;
  border-radius: 10px;
  animation: fadeIn 1s ease-out 0.5s both;
}

.announcement-header {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

.announcement-header .logo {
  font-size: 12px;
  padding: 5px 8px;
  margin-right: 10px;
  animation: none;
}

.announcement-header h3 {
  font-size: 14px;
  font-weight: 600;
}

.announcements p {
  font-size: 12px;
  color: #666;
  margin-bottom: 15px;
}

.create-btn {
  background-color: #7e57c2;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 12px;
  cursor: pointer;
  margin-bottom: 15px;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.create-btn:hover {
  background-color: #6a46b0;
  transform: translateY(-2px);
}

.create-btn:active {
  transform: translateY(0);
}

.read-by {
  display: flex;
  align-items: center;
  font-size: 12px;
  color: #999;
}

.dashboard {
  flex: 1;
  padding: 20px;
  overflow-x: hidden;
}

.dashboard-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
  gap: 15px;
  animation: slideInDown 0.7s ease-out;
}

.welcome-message {
  font-size: 24px;
  font-weight: 600;
}

.date-export {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
  animation: slideInRight 0.8s ease-out;
}

.date-range {
  border: 1px solid #e0e0e0;
  padding: 8px 15px;
  border-radius: 8px;
  color: #666;
  transition: border-color 0.3s ease;
}

.date-range:hover {
  border-color: #7e57c2;
}

.export-btn {
  background-color: #7e57c2;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 8px;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.export-btn:hover {
  background-color: #6a46b0;
  transform: translateY(-2px);
}

.export-btn:active {
  transform: translateY(0);
}

.export-btn::before {
  content: "⬇️";
  margin-right: 5px;
  font-size: 14px;
}

.export-btn-sm {
  background-color: white;
  color: #666;
  border: 1px solid #e0e0e0;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.export-btn-sm:hover {
  background-color: #f5f5f7;
  transform: translateY(-2px);
}

.cards-row {
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
  flex-wrap: wrap;
}

.card {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  padding: 20px;
  flex: 1;
  min-width: 250px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  animation: scaleIn 0.5s ease-out;
  animation-fill-mode: both;
}

.cards-row .card:nth-child(1) { animation-delay: 0.1s; }
.cards-row .card:nth-child(2) { animation-delay: 0.3s; }
.cards-row .card:nth-child(3) { animation-delay: 0.5s; }
.cards-row .card:nth-child(4) { animation-delay: 0.7s; }

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.card.wide {
  flex: 0 0 calc(50% - 10px);
  min-width: 300px;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
  flex-wrap: wrap;
  gap: 10px;
}

.card-header h3 {
  font-size: 18px;
  font-weight: 600;
}

.more-btn {
  background: none;
  border: none;
  color: #999;
  font-size: 18px;
  cursor: pointer;
  transition: color 0.3s ease, transform 0.3s ease;
}

.more-btn:hover {
  color: #7e57c2;
  transform: scale(1.1);
}

.employee-stats {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.employee-stat {
  display: flex;
  align-items: baseline;
  gap: 10px;
  flex-wrap: wrap;
  animation: slideInRight 0.7s ease-out;
  animation-fill-mode: both;
}

.employee-stat:nth-child(1) { animation-delay: 0.2s; }
.employee-stat:nth-child(2) { animation-delay: 0.4s; }
.employee-stat:nth-child(3) { animation-delay: 0.6s; }

.stat-number {
  font-size: 28px;
  font-weight: 700;
}

.stat-change {
  font-size: 14px;
}

.increase {
  color: #4caf50;
}

.decrease {
  color: #f44336;
}

.stat-label {
  margin-left: auto;
  color: #999;
  font-size: 14px;
}

.attendance-stats {
  display: flex;
  flex-direction: column;
  gap: 10px;
  animation: fadeIn 0.8s ease-out 0.3s both;
}

.attendance-percent {
  font-size: 28px;
  font-weight: 700;
}

.attendance-change {
  font-size: 14px;
}

.progress-bar {
  height: 5px;
  background-color: #e0e0e0;
  border-radius: 3px;
  margin: 5px 0 10px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(to right, #a57ced, #7e57c2);
  border-radius: 3px;
  animation: progressLoad 1.5s ease-out;
}

.attendance-labels {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.label {
  display: flex;
  align-items: center;
  font-size: 14px;
  color: #666;
  animation: fadeIn 1s ease-out;
}

/* Staggered animation for labels */
.sick-leave { animation-delay: 0.5s; }
.day-off { animation-delay: 0.7s; }
.on-time { animation-delay: 0.9s; }

.label::before {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 5px;
}

.sick-leave::before {
  background-color: #f44336;
}

.day-off::before {
  background-color: #ff9800;
}

.on-time::before {
  background-color: #7e57c2;
}

.devices-stats {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 15px;
  animation: fadeIn 0.8s ease-out 0.4s both;
}

.gauge-container {
  flex: 0 0 40%;
  min-width: 120px;
  animation: scaleIn 0.7s ease-out 0.5s both;
}

.gauge {
  position: relative;
  width: 120px;
  height: 60px;
  border-radius: 60px 60px 0 0;
  background: conic-gradient(
    from 180deg,
    #7e57c2 0%,
    #a57ced 50%,
    #ffca28 80%,
    #ff9800 100%
  );
  margin: 0 auto;
}

.gauge::before {
  content: "";
  position: absolute;
  width: 90px;
  height: 45px;
  top: 5px;
  left: 15px;
  background-color: white;
  border-radius: 45px 45px 0 0;
}

.gauge-value {
  position: absolute;
  top: 20px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 20px;
  font-weight: 700;
  z-index: 1;
  animation: fadeIn 1s ease-out 1s both;
}

.gauge-label {
  font-size: 12px;
  text-align: center;
  color: #999;
  margin-top: 5px;
}

.devices-list {
  flex: 0 0 60%;
  min-width: 120px;
}

.device-item {
  display: flex;
  align-items: center;
  margin-bottom: 8px;
  animation: slideInRight 0.5s ease-out;
  animation-fill-mode: both;
}

/* Staggered animation for device items */
.device-item:nth-child(1) { animation-delay: 0.5s; }
.device-item:nth-child(2) { animation-delay: 0.7s; }
.device-item:nth-child(3) { animation-delay: 0.9s; }
.device-item:nth-child(4) { animation-delay: 1.1s; }

.device-count {
  font-size: 16px;
  font-weight: 600;
  width: 30px;
}

.device-name {
  color: #666;
  margin-left: 10px;
}

.performance-content {
  overflow-x: auto;
}

.performance-header {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
  gap: 15px;
  animation: fadeIn 0.8s ease-out 0.3s both;
}

.performance-percent {
  font-size: 32px;
  font-weight: 700;
  margin-right: 20px;
}

.performance-text {
  color: #666;
  font-size: 14px;
  flex: 1;
  min-width: 200px;
}

.performance-list {
  margin-bottom: 20px;
}

.performance-item {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
  flex-wrap: wrap;
  gap: 10px;
  animation: slideInRight 0.5s ease-out;
  animation-fill-mode: both;
}

/* Staggered animation for performance items */
.performance-item:nth-child(1) { animation-delay: 0.4s; }
.performance-item:nth-child(2) { animation-delay: 0.6s; }
.performance-item:nth-child(3) { animation-delay: 0.8s; }
.performance-item:nth-child(4) { animation-delay: 1.0s; }

.employee-name {
  width: 120px;
  font-size: 14px;
}

.performance-bars {
  flex: 1;
  display: flex;
  height: 8px;
  gap: 5px;
  min-width: 200px;
}

.bar {
  height: 100%;
  border-radius: 4px;
  animation: barGrow 1s ease-out;
}

.task-bar {
  background-color: #7e57c2;
  width: 70px;
}

.presence-bar {
  background-color: #2196f3;
  width: 60px;
  animation-delay: 0.2s;
}

.meeting-bar {
  background-color: #26a69a;
  width: 50px;
  animation-delay: 0.4s;
}

.performance-legend {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  animation: fadeIn 1s ease-out 1s both;
}

.legend-item {
  display: flex;
  align-items: center;
  font-size: 12px;
  color: #666;
}

.legend-color {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 5px;
}

.task-color {
  background-color: #7e57c2;
}

.presence-color {
  background-color: #2196f3;
}

.meeting-color {
  background-color: #26a69a;
}

.income-color {
  background-color: #7e57c2;
}

.expense-color {
  background-color: #2196f3;
}

.advanced-filter {
  background: none;
  border: none;
  color: #7e57c2;
  font-size: 14px;
  cursor: pointer;
  transition: color 0.3s ease, transform 0.3s ease;
}

.advanced-filter:hover {
  color: #6a46b0;
  transform: translateY(-2px);
}

.chart-content {
  display: flex;
  overflow-x: auto;
  animation: fadeIn 1s ease-out 0.5s both;
}

.y-axis {
  display: flex;
  flex-direction: column-reverse;
  justify-content: space-between;
  padding-right: 10px;
  height: 250px;
}

.axis-label {
  font-size: 12px;
  color: #999;
}

.chart-area {
  flex: 1;
  height: 250px;
  min-width: 500px;
}

.chart-columns {
  display: flex;
  justify-content: space-between;
  height: 100%;
}

.chart-column {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
}

.income-bar, .expense-bar {
  width: 15px;
  border-radius: 2px 2px 0 0;
  animation: barGrow 1s ease-out;
  animation-fill-mode: both;
}

/* Staggered animation for chart columns */
.chart-column:nth-child(1) .income-bar, .chart-column:nth-child(1) .expense-bar { animation-delay: 0.2s; }
.chart-column:nth-child(2) .income-bar, .chart-column:nth-child(2) .expense-bar { animation-delay: 0.4s; }
.chart-column:nth-child(3) .income-bar, .chart-column:nth-child(3) .expense-bar { animation-delay: 0.6s; }
.chart-column:nth-child(4) .income-bar, .chart-column:nth-child(4) .expense-bar { animation-delay: 0.8s; }
.chart-column:nth-child(5) .income-bar, .chart-column:nth-child(5) .expense-bar { animation-delay: 1.0s; }
.chart-column:nth-child(6) .income-bar, .chart-column:nth-child(6) .expense-bar { animation-delay: 1.2s; }

.income-bar {
  background-color: #7e57c2;
  height: 50px;
  margin-bottom: 2px;
}

.expense-bar {
  background-color: #2196f3;
  height: 30px;
  position: relative;
}

.expense-bar::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100%;
  background: repeating-linear-gradient(
    45deg,
    rgba(255, 255, 255, 0.2),
    rgba(255, 255, 255, 0.2) 3px,
    transparent 3px,
    transparent 6px
  );
}

.income-bar.tall {
  height: 100px;
}

.expense-bar.tall {
  height: 60px;
}

.month-label {
  font-size: 12px;
  color: #999;
  margin-top: 5px;
  animation: fadeIn 1s ease-out 1.2s both;
}

.chart-info {
  margin-top: 20px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 15px;
  animation: fadeIn 1s ease-out 1.3s both;
}

.chart-month {
  font-weight: 600;
  margin-right: 30px;
}

.chart-legend {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.chart-legend .legend-item {
  align-items: center;
}

.amount {
  font-weight: 600;
  margin-left: 5px;
}

.employee-table-section {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  padding: 20px;
  margin-top: 20px;
  overflow-x: auto;
  animation: slideInUp 0.8s ease-out;
}

.table-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
  gap: 15px;
}

.table-header h3 {
  font-size: 18px;
  font-weight: 600;
}

.table-actions {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-wrap: wrap;
}

.filter-select {
  padding: 6px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 6px;
  color: #666;
  font-size: 14px;
  transition: border-color 0.3s ease;
}

.filter-select:hover, .filter-select:focus {
  border-color: #7e57c2;
}

.employee-table {
  width: 100%;
  border-collapse: collapse;
  min-width: 800px;
}

.employee-table th {
  text-align: left;
  padding: 12px 15px;
  font-weight: 500;
  color: #666;
  border-bottom: 1px solid #e0e0e0;
}

.employee-table td {
  padding: 12px 15px;
  border-bottom: 1px solid #f5f5f7;
}

.employee-table tr {
  animation: fadeIn 0.5s ease-out;
  animation-fill-mode: both;
}

/* Staggered animation for table rows */
.employee-table tr:nth-child(1) { animation-delay: 0.3s; }
.employee-table tr:nth-child(2) { animation-delay: 0.4s; }
.employee-table tr:nth-child(3) { animation-delay: 0.5s; }
.employee-table tr:nth-child(4) { animation-delay: 0.6s; }
.employee-table tr:nth-child(5) { animation-delay: 0.7s; }
.employee-table tr:nth-child(6) { animation-delay: 0.8s; }
.employee-table tr:nth-child(7) { animation-delay: 0.9s; }
.employee-table tr:nth-child(8) { animation-delay: 1.0s; }

.employee-table tr:hover {
  background-color: #f9f9fb;
}

.employee-name {
  display: flex;
  align-items: center;
}

.employee-avatar {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin-right: 10px;
  transition: transform 0.3s ease;
}

.employee-name:hover .employee-avatar {
  transform: scale(1.1);
}

.status {
  display: inline-block;
  padding: 5px 10px;
  border-radius: 15px;
  font-size: 12px;
  font-weight: 500;
  transition: transform 0.3s ease;
}

.status:hover {
  transform: translateY(-2px);
}

.status.fulltime {
  background-color: #e8f5e9;
  color: #4caf50;
}

.status.freelance {
  background-color: #fff8e1;
  color: #ff9800;
}

.actions {
  display: flex;
  gap: 10px;
}

.view-btn {
  background: none;
  border: none;
  cursor: pointer;
  color: #666;
  transition: color 0.3s ease, transform 0.3s ease;
}

.view-btn:hover {
  color: #7e57c2;
  transform: scale(1.1);
}
.mobile-menu-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  margin-right: 15px;
}

@media (max-width: 1400px) {
  .card.wide {
    flex: 1 1 calc(50% - 20px);
    min-width: 400px;
  }
  
  .card {
    flex: 1 1 calc(33.33% - 20px);
    min-width: 250px;
  }
}

@media (max-width: 1200px) {
  .card.wide {
    flex: 1 1 100%;
  }
  
  .card {
    flex: 1 1 calc(50% - 20px);
  }
  
  .nav-right .search-container {
    order: -1;
    flex: 1 1 100%;
    margin-bottom: 10px;
  }
  
  .nav-right .search-input {
    width: 100%;
  }
  
  .table-actions {
    justify-content: space-between;
    width: 100%;
  }
  
  .table-actions .search-container.small {
    flex: 1;
  }
  
  .table-actions .search-container.small .search-input {
    width: 100%;
  }
}

@media (max-width: 992px) {
  .mobile-menu-toggle {
    display: block;
  }
  
  .main-content {
    position: relative;
  }
  
  .sidebar {
    position: fixed;
    left: -300px;
    top: 0;
    height: 100vh;
    z-index: 100;
    overflow-y: auto;
    transition: left 0.3s ease;
  }
  
  .sidebar.active {
    left: 0;
  }
  
  .sidebar-overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 99;
  }
  
  .sidebar-overlay.active {
    display: block;
  }
  
  .dashboard {
    width: 100%;
  }
  
  .cards-row {
    flex-direction: column;
  }
  
  .card, .card.wide {
    flex: 1 1 100%;
  }
  
  .performance-bars {
    width: 100%;
  }
  
  .devices-stats {
    justify-content: center;
  }
  
  .gauge-container, .devices-list {
    flex: 0 0 100%;
    text-align: center;
  }
  
  .device-item {
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .navbar {
    padding: 15px 10px;
  }
  
  .logo-container {
    width: 100%;
    justify-content: space-between;
    margin-bottom: 10px;
  }
  
  .nav-right {
    width: 100%;
    justify-content: space-between;
  }
  
  .user-avatars {
    display: none;
  }
  
  .dashboard-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .welcome-message {
    font-size: 20px;
  }
  
  .date-export {
    width: 100%;
    justify-content: space-between;
  }
  
  .card-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .attendance-labels {
    justify-content: space-between;
  }
  
  .performance-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .performance-percent {
    margin-right: 0;
  }
  
  .performance-legend {
    justify-content: space-between;
  }
  
  .table-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .employee-table th, .employee-table td {
    padding: 8px 10px;
    font-size: 14px;
  }
  
  .employee-avatar {
    width: 25px;
    height: 25px;
  }
  
  .employee-name span {
    max-width: 100px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
}

@media (max-width: 576px) {
  .navbar {
    padding: 10px;
  }
  
  .search-container .search-input {
    width: 100%;
    max-width: none;
  }
  
  .nav-right {
    gap: 8px;
  }
  
  .date-range, .export-btn {
    width: 100%;
    text-align: center;
  }
  
  .card {
    padding: 15px;
  }
  
  .status {
    padding: 3px 8px;
    font-size: 10px;
  }
  
  .actions {
    flex-direction: column;
    gap: 5px;
  }
}

.mobile-sidebar-close {
  display: none;
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 24px;
  color: #666;
  cursor: pointer;
}

@media (max-width: 992px) {
  .mobile-sidebar-close {
    display: block;
  }
  
  .sidebar {
    padding-top: 50px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .sidebar, .progress-fill, .income-bar, .expense-bar {
    transition: none;
  }
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: #121212;
    color: #f5f5f7;
  }
  
  .navbar, .sidebar, .card, .employee-table-section {
    background-color: #1e1e1e;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  }
  
  .search-input, .date-range, .filter-select {
    background-color: #2d2d2d;
    border-color: #444;
    color: #f5f5f7;
  }
  
  .sidebar-link, .card-header h3, .welcome-message, .employee-name span {
    color: #f5f5f7;
  }
  
  .sidebar-link:hover, .sidebar-link.active {
    background-color: #2d2d2d;
  }
  
  .sidebar-link.active {
    color: #a57ced;
  }
  
  .employee-table th, .employee-table td {
    border-color: #333;
    color: #ddd;
  }
  
  .invite-btn, .export-btn-sm {
    background-color: #2d2d2d;
    color: #f5f5f7;
  }
  
  .announcements {
    background-color: #2d2d2d;
  }
  
  .gauge::before {
    background-color: #1e1e1e;
  }
  
  .stat-label, .device-name, .axis-label, .month-label, .performance-text {
    color: #aaa;
  }
}
</style>