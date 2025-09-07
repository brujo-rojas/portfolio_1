<template>
  <nav class="navbar-glass">
    <div class="nav-container">
      <router-link to="/" class="nav-link">PR</router-link>
      <router-link to="/examples" class="nav-link">Portfolio</router-link>
    </div>
  </nav>
  <router-view />
</template>

<style lang="scss">
.navbar-glass {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(26, 28, 32, 0.8);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  z-index: 1000;
  padding: 1rem 0;
  
  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 2rem;
    
    .nav-link {
      color: rgba(255, 255, 255, 0.8);
      text-decoration: none;
      padding: 0.5rem 1rem;
      border-radius: 8px;
      transition: all 0.3s ease;
      font-weight: 500;
      
      &:hover {
        color: white;
        background: rgba(255, 255, 255, 0.1);
      }
      
      &.router-link-active {
        color: white;
        background: rgba(255, 255, 255, 0.15);
      }
    }
  }
}

// Agregar padding-top al cuerpo para compensar navbar fija
#app {
  padding-top: 80px;
}
</style>
