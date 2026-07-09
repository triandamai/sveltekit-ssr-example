<script>
  import { page } from '$app/stores';
</script>

<main class="container">
  <div class="card">
    <nav class="nav-container">
      <a class="nav-btn {$page.url.pathname === '/' ? 'active' : ''}" href="/">Home</a>
      <a class="nav-btn {$page.url.pathname === '/about' ? 'active' : ''}" href="/about">About</a>
      <a class="nav-btn {$page.url.pathname === '/login' ? 'active' : ''}" href="/login">Login</a>
    </nav>

    <slot></slot>
  </div>
</main>

<style>
:global(body) {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #1e0b00 0%, #2d1200 100%);
  color: #ffebe0;
  font-family: system-ui, -apple-system, sans-serif;
  padding: 20px;
}
.card {
  background: rgba(45, 18, 0, 0.4);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 62, 0, 0.15);
  border-radius: 24px;
  padding: 40px;
  max-width: 550px;
  width: 100%;
  text-align: center;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.6);
  display: flex;
  flex-direction: column;
  align-items: center;
}
.nav-container {
  display: inline-flex;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(8px);
  padding: 6px;
  border-radius: 30px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  margin-bottom: 30px;
}
.nav-btn {
  background: transparent;
  border: none;
  color: rgba(255, 235, 224, 0.6);
  padding: 8px 20px;
  font-size: 0.9rem;
  font-weight: 600;
  border-radius: 20px;
  cursor: pointer;
  transition: all 0.25s ease;
  outline: none;
  text-decoration: none;
  display: inline-block;
}
.nav-btn:hover {
  color: #fff;
}
.nav-btn.active {
  background: linear-gradient(to right, #ff3e00, #ff6a00);
  color: white;
  box-shadow: 0 4px 12px rgba(255, 62, 0, 0.3);
}
</style>
