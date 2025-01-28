<script>
  let isMenuOpen = false;
  const toggleMenu = () => isMenuOpen = !isMenuOpen;
</script>

<header class="header">
  <nav class="nav">
    <div class="nav-brand"> </div> <!-- Personal Portfolio -->
    <button class="menu-button" on:click={toggleMenu}>
      <span class="menu-icon">☰</span>
    </button>
    <ul class="nav-links" class:active={isMenuOpen}>
      <li><a href="#home">Home</a></li>
      <li><a href="#projects">Projects</a></li>
    </ul>
  </nav>
</header>

<style>
  .header {
    background: #ffffff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000;
  }

  .nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .nav-brand {
    font-size: 1.5rem;
    font-weight: bold;
  }

  .menu-button {
    display: none;
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
  }

  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .nav-links a {
    color: #333;
    text-decoration: none;
    font-weight: 500;
  }

  @media (max-width: 768px) {
    .menu-button {
      display: block;
    }

    .nav-links {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background: white;
      padding: 1rem;
      flex-direction: column;
      align-items: center;
    }

    .nav-links.active {
      display: flex;
    }
  }
</style>