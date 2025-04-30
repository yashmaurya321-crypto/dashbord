<template>
    <div class="sidebar">
        <div class="sidebar-section">
          <a href="#" class="sidebar-link active">
            <span class="sidebar-icon">🏠</span>
            <span>Dashboard</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📋</span>
            <span>Projects</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📅</span>
            <span>Calendar</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">🏖️</span>
            <span>Leave Management</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">⚙️</span>
            <span>Settings</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">🔔</span>
            <span>Notification</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">❓</span>
            <span>Help & Center</span>
          </a>
        </div>

        <div class="sidebar-section">
          <h3 class="sidebar-title">TEAM MANAGEMENT</h3>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📊</span>
            <span>Performance</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">💰</span>
            <span>Payrolls</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📝</span>
            <span>Invoices</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">👥</span>
            <span>Employees</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">🎯</span>
            <span>Recruitment & Hiring</span>
          </a>
        </div>

        <div class="sidebar-section">
          <h3 class="sidebar-title">LIST</h3>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">💵</span>
            <span>Salary Information</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📊</span>
            <span>Compensation Breakdown</span>
          </a>
          <a href="#" class="sidebar-link">
            <span class="sidebar-icon">📁</span>
            <span>Project-specific Data</span>
          </a>
        </div>

        <div class="announcements">
          <div class="announcement-header">
            <div class="logo">
              <span>TurHR</span>
            </div>
            <h3>Announcements</h3>
          </div>
          <p>Stay updated with TurHR</p>
          <button class="create-btn">Create Now</button>
          <div class="read-by">
            <span>Read by:</span>
            <div class="user-avatars small">
              <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
              <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
              <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
              <span class="avatar-count">+10</span>
            </div>
          </div>
        </div>
      </div>
</template>

<script>
export default {
  name: 'RightBar'  
}
</script>