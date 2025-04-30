<template>
     <nav class="navbar">
      <div class="logo-container">
        <div class="logo">
          <span>TurHR</span>
        </div>
        <h1 class="page-title">Dashboard</h1>
      </div>
      <div class="nav-right">
        <div class="search-container">
          <input type="text" placeholder="Quick Search..." class="search-input">
          <span class="search-icon">🔍</span>
        </div>
        <button class="icon-btn">📩</button>
        <button class="icon-btn">🔄</button>
        <div class="user-avatars">
          <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
          <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
          <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D" alt="User" class="avatar">
          <span class="avatar-count">+10</span>
        </div>
        <button class="invite-btn">Invite</button>
      </div>
    </nav>
</template>

<script>
export default {
  name: 'AppNavbar'  
}
</script>