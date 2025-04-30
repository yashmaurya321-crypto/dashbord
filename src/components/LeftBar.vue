<template>
    <div class="dashboard">
        <div class="dashboard-header">
          <h2 class="welcome-message">Good Morning, {{ currentUser.name }}</h2>
          <div class="date-export">
            <div class="date-range">{{ dateRange }}</div>
            <button class="export-btn" @click="exportData">Export Data</button>
          </div>
        </div>

        <div class="cards-row">
          
          <div class="card">
            <div class="card-header">
              <h3>Total Employees</h3>
              <button class="more-btn">...</button>
            </div>
            <div class="employee-stats">
              <div class="employee-stat">
                <div class="stat-number">{{ employees.fulltime }}</div>
                <div class="stat-change increase">{{ employees.fulltimeChange }}</div>
                <div class="stat-label">Fulltime Employee</div>
              </div>
              <div class="employee-stat">
                <div class="stat-number">{{ employees.freelance }}</div>
                <div class="stat-change decrease">{{ employees.freelanceChange }}</div>
                <div class="stat-label">Freelance Employee</div>
              </div>
            </div>
          </div>

          <div class="card">
            <div class="card-header">
              <h3>Attendance Overview</h3>
              <button class="more-btn">...</button>
            </div>
            <div class="attendance-stats">
              <div class="attendance-percent">{{ attendance.percentage }}</div>
              <div class="attendance-change increase">{{ attendance.change }} since last month</div>
              <div class="progress-bar">
                <div class="progress-fill" :style="{ width: attendance.percentage }"></div>
              </div>
              <div class="attendance-labels">
                <span class="label sick-leave">Sick Leave</span>
                <span class="label day-off">Day Off</span>
                <span class="label on-time">On time</span>
              </div>
            </div>
          </div>

          <div class="card">
            <div class="card-header">
              <h3>Today Used Devices</h3>
              <button class="more-btn">...</button>
            </div>
            <div class="devices-stats">
              <div class="gauge-container">
                <div class="gauge">
                  <div class="gauge-value">{{ devices.overall }}</div>
                  <div class="gauge-label">Overall</div>
                </div>
              </div>
              <div class="devices-list">
                <div v-for="(device, index) in devices.items" :key="index" class="device-item">
                  <div :class="['device-count', device.change]">{{ device.count }}</div>
                  <div class="device-name">{{ device.name }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="cards-row">
         
          <div class="card wide">
            <div class="card-header">
              <h3>Employee Performance Ratings</h3>
              <button class="more-btn">...</button>
            </div>
            <div class="performance-content">
              <div class="performance-header">
                <div class="performance-percent">{{ performance.percentage }}</div>
                <p class="performance-text">
                  {{ performance.text }}
                </p>
              </div>
              <div class="performance-list">
                <div v-for="(emp, index) in performance.employees" :key="index" class="performance-item">
                  <div class="employee-name">{{ emp.name }}</div>
                  <div class="performance-bars">
                    <div class="bar task-bar" :style="{ width: emp.task + 'px' }"></div>
                    <div class="bar presence-bar" :style="{ width: emp.presence + 'px' }"></div>
                    <div class="bar meeting-bar" :style="{ width: emp.meeting + 'px' }"></div>
                  </div>
                </div>
              </div>
              <div class="performance-legend">
                <div class="legend-item">
                  <span class="legend-color task-color"></span>
                  <span>Task completed</span>
                </div>
                <div class="legend-item">
                  <span class="legend-color presence-color"></span>
                  <span>Presence</span>
                </div>
                <div class="legend-item">
                  <span class="legend-color meeting-color"></span>
                  <span>Completed Meeting</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Income Statistics Card -->
          <div class="card wide">
            <div class="card-header">
              <h3>Income Statistics</h3>
              <button class="advanced-filter">Advanced Filter</button>
            </div>
            <div class="chart-content">
              <div class="y-axis">
                <div class="axis-label">$13k</div>
                <div class="axis-label">$11k</div>
                <div class="axis-label">$9k</div>
                <div class="axis-label">$7k</div>
                <div class="axis-label">$5k</div>
                <div class="axis-label">$3k</div>
                <div class="axis-label">$0</div>
              </div>
              <div class="chart-area">
                <div class="chart-columns">
                  <div v-for="(item, index) in income.chartData" :key="index" class="chart-column">
                    <div class="income-bar" :class="{ 'tall': item.income > 75 }" 
                         :style="{ height: item.income + 'px' }"></div>
                    <div class="expense-bar" :class="{ 'tall': item.expense > 50 }"
                         :style="{ height: item.expense + 'px' }"></div>
                    <div class="month-label">{{ item.month }}</div>
                  </div>
                </div>
              </div>
             
            </div>
          </div>
        </div>

        <div class="employee-table-section">
          <div class="table-header">
            <h3>All Employees</h3>
            <div class="table-actions">
              <div class="search-container small">
                <input type="text" placeholder="Search Employee" class="search-input">
                <span class="search-icon">🔍</span>
              </div>
              <select class="filter-select">
                <option>All Status</option>
              </select>
              <select class="filter-select">
                <option>All Role</option>
              </select>
              <button class="export-btn-sm">Export</button>
            </div>
          </div>
          <table class="employee-table">
            <thead>
              <tr>
                <th><input type="checkbox" /></th>
                <th>Employee ID</th>
                <th>Employee name</th>
                <th>Email</th>
                <th>Role</th>
                <th>Departments</th>
                <th>Status</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><input type="checkbox" /></td>
                <td>TUR871219</td>
                <td class="employee-name">
                  <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="Ahsan" class="employee-avatar">
                  <span>Ahsan Tapader</span>
                </td>
                <td>ahsan.tur@mail.com</td>
                <td>Sr UI/UX Designer</td>
                <td>Team Projects</td>
                <td><span class="status fulltime">Full-time</span></td>
                <td class="actions">
                  <button class="view-btn">👁️</button>
                  <button class="more-btn">...</button>
                </td>
              </tr>
              <tr>
                <td><input type="checkbox" /></td>
                <td>TUR185103</td>
                <td class="employee-name">
                  <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="Washi" class="employee-avatar">
                  <span>Washi Bin M.</span>
                </td>
                <td>washi.tur@mail.com</td>
                <td>Lead Product Designer</td>
                <td>Head of Projects</td>
                <td><span class="status fulltime">Full-time</span></td>
                <td class="actions">
                  <button class="view-btn">👁️</button>
                  <button class="more-btn">...</button>
                </td>
              </tr>
              <tr>
                <td><input type="checkbox" /></td>
                <td>TUR715481</td>
                <td class="employee-name">
                  <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="Keyes" class="employee-avatar">
                  <span>Keyes Ahmed</span>
                </td>
                <td>keyes.tur@mail.com</td>
                <td>Sr UX Designer</td>
                <td>Client & Team Work</td>
                <td><span class="status fulltime">Full-time</span></td>
                <td class="actions">
                  <button class="view-btn">👁️</button>
                  <button class="more-btn">...</button>
                </td>
              </tr>
              <tr>
                <td><input type="checkbox" /></td>
                <td>TUR016481</td>
                <td class="employee-name">
                  <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="Turja" class="employee-avatar">
                  <span>Turja Sen Das</span>
                </td>
                <td>Turja.tur@mail.com</td>
                <td>Mid UI Designer</td>
                <td>Case Study</td>
                <td><span class="status freelance">Freelance</span></td>
                <td class="actions">
                  <button class="view-btn">👁️</button>
                  <button class="more-btn">...</button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
</template>

<script>

export default {
  name: 'LeftBar',
 
  data() {
    return {
      currentUser: {
        name: 'Turja Sen',
        avatar: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D'
      },
      dateRange: '01 Sep - 15 Sep 2024',
      employees: {
        fulltime: 150,
        fulltimeChange: '+50',
        freelance: 50,
        freelanceChange: '-10'
      },
      attendance: {
        percentage: '90%',
        change: '+20%'
      },
      devices: {
        overall: 100,
        items: [
          { name: 'Macbook', count: 80, change: 'increase' },
          { name: 'Keyboard', count: 13, change: 'increase' },
          { name: 'Headphones', count: 7, change: 'increase' }
        ]
      },
      performance: {
        percentage: '98%',
        text: 'At Tur Agency, we\'re proud of our employees\' consistent punctuality and quality work.',
        employees: [
          { name: 'Ahsan Tapader', task: 70, presence: 60, meeting: 50 },
          { name: 'Keyes Ahmed', task: 65, presence: 70, meeting: 55 },
          { name: 'Washi Bin M.', task: 75, presence: 50, meeting: 60 },
          { name: 'Mir Muhsin', task: 60, presence: 65, meeting: 50 },
          { name: 'Turja Sen Das', task: 70, presence: 60, meeting: 55 }
        ]
      },
      income: {
        month: 'May 2024',
        income: '$2198.11',
        expense: '$733.43',
        chartData: [
          { month: 'Jan', income: 30, expense: 20 },
          { month: 'Feb', income: 50, expense: 30 },
          { month: 'Mar', income: 70, expense: 40 },
          { month: 'Apr', income: 100, expense: 60 },
          { month: 'May', income: 50, expense: 30 },
          { month: 'Jun', income: 40, expense: 20 },
          { month: 'Jul', income: 80, expense: 40 },
          { month: 'Aug', income: 50, expense: 30 },
          { month: 'Sep', income: 60, expense: 40 },
          { month: 'Oct', income: 40, expense: 20 },
          { month: 'Nov', income: 50, expense: 30 },
          { month: 'Dec', income: 60, expense: 40 }
        ]
      },
      employeeList: [
        { id: 'TUR871219', name: 'Ahsan Tapader', email: 'ahsan.tur@mail.com', role: 'Sr UI/UX Designer', department: 'Team Projects', status: 'Full-time' },
        { id: 'TUR185103', name: 'Washi Bin M.', email: 'washi.tur@mail.com', role: 'Lead Product Designer', department: 'Head of Projects', status: 'Full-time' },
        { id: 'TUR715481', name: 'Keyes Ahmed', email: 'keyes.tur@mail.com', role: 'Sr UX Designer', department: 'Client & Team Work', status: 'Full-time' },
        { id: 'TUR016481', name: 'Turja Sen Das', email: 'Turja.tur@mail.com', role: 'Mid UI Designer', department: 'Case Study', status: 'Freelance' }
      ],
      searchQuery: '',
      selectedStatus: 'All Status',
      selectedRole: 'All Role'
    }
  },
  computed: {
    filteredEmployees() {
      let result = this.employeeList;
      
      if (this.searchQuery) {
        const query = this.searchQuery.toLowerCase();
        result = result.filter(emp => 
          emp.name.toLowerCase().includes(query) || 
          emp.email.toLowerCase().includes(query) ||
          emp.id.toLowerCase().includes(query)
        );
      }
      
      if (this.selectedStatus !== 'All Status') {
        result = result.filter(emp => emp.status === this.selectedStatus);
      }
      
      if (this.selectedRole !== 'All Role') {
        result = result.filter(emp => emp.role.includes(this.selectedRole));
      }
      
      return result;
    }
  },
  methods: {
    exportData() {
      alert('Exporting data for ' + this.dateRange);
    },
    viewEmployee(id) {
      alert('Viewing employee details for ID: ' + id);
    },
    moreOptions(id) {
      alert('Showing more options for employee ID: ' + id);
    }
  }
}
</script>