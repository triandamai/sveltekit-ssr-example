<script>
  export let data;
  let activeTab = 'home';
</script>

<main class="container">
  <div class="card">
    <nav class="nav-container">
      <button class="nav-btn {activeTab === 'home' ? 'active' : ''}" on:click={() => activeTab = 'home'}>Home</button>
      <button class="nav-btn {activeTab === 'about' ? 'active' : ''}" on:click={() => activeTab = 'about'}>About</button>
    </nav>

    {#if activeTab === 'home'}
      <div>
        <div class="logo">
          <svg xmlns="http://www.w3.org/2000/svg" width="80" height="80" viewBox="0 0 256 256">
            <path fill="#FF3E00" d="M128 0C57.3 0 0 57.3 0 128s57.3 128 128 128s128-57.3 128-128S198.7 0 128 0m0 192c-35.3 0-64-28.7-64-64s28.7-64 64-64s64 28.7 64 64s-28.7 64-64 64"/>
          </svg>
        </div>
        <h1>SvelteKit SSR</h1>
        <p class="subtitle">Server-Side Rendered SvelteKit App, deployed via Shipyard.</p>
        
        <div class="info-box">
          <h3>Server-Rendered Props</h3>
          <p class="time">{data.serverTime}</p>
        </div>

        <div class="grid">
          <div class="item">
            <h4>Node Adapter</h4>
            <p>Built with @sveltejs/adapter-node, producing a standalone Node server application.</p>
          </div>
          <div class="item">
            <h4>Universal SSR</h4>
            <p>Dynamic execution of pages on the server with seamless hydration in the browser.</p>
          </div>
        </div>
      </div>
    {:else if activeTab === 'about'}
      <div>
        <div class="logo">
          <svg xmlns="http://www.w3.org/2000/svg" width="80" height="80" viewBox="0 0 256 256">
            <path fill="#FF3E00" d="M128 0C57.3 0 0 57.3 0 128s57.3 128 128 128s128-57.3 128-128S198.7 0 128 0m0 192c-35.3 0-64-28.7-64-64s28.7-64 64-64s64 28.7 64 64s-28.7 64-64 64"/>
          </svg>
        </div>
        <h1>About SvelteKit</h1>
        <p class="subtitle">SvelteKit is a framework for building web applications of all sizes.</p>
        
        <div class="info-box">
          <h3>Project Details</h3>
          <p class="time" style="font-family: inherit; font-size: 0.95rem;">
            SvelteKit compiles components down to tiny, finger-sized vanilla JavaScript files for unmatched browser speed and responsiveness.
          </p>
        </div>

        <div style="font-size: 0.85rem; color: #ffc4a8; margin-top: 20px;">
          Learn more at <a href="https://kit.svelte.dev" target="_blank" style="color: #ff3e00; text-decoration: none; font-weight: bold;">kit.svelte.dev</a>
        </div>
      </div>
    {/if}
  </div>
</main>

<style>
:global(body) {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
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
}
.nav-btn:hover {
  color: #fff;
}
.nav-btn.active {
  background: linear-gradient(to right, #ff3e00, #ff6a00);
  color: white;
  box-shadow: 0 4px 12px rgba(255, 62, 0, 0.3);
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
.logo {
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
}
h1 {
  font-size: 2.5rem;
  font-weight: 800;
  margin: 0 0 10px 0;
  background: linear-gradient(to right, #ff3e00, #ff6a00);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.subtitle {
  color: #ffc4a8;
  font-size: 1.1rem;
  margin: 0 0 30px 0;
  opacity: 0.9;
}
.info-box {
  background: rgba(30, 12, 0, 0.6);
  border-radius: 16px;
  padding: 20px;
  margin-bottom: 30px;
  border: 1px solid rgba(255, 62, 0, 0.1);
}
.info-box h3 {
  margin: 0 0 10px 0;
  color: #ff3e00;
  font-size: 1rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.time {
  font-family: monospace;
  font-size: 1.1rem;
  margin: 0;
  color: #ffc4a8;
}
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  text-align: left;
}
.item {
  background: rgba(30, 12, 0, 0.3);
  padding: 16px;
  border-radius: 12px;
  border: 1px solid rgba(255, 62, 0, 0.05);
}
.item h4 {
  margin: 0 0 6px 0;
  color: #fff1eb;
}
.item p {
  margin: 0;
  font-size: 0.85rem;
  color: #ffc4a8;
  opacity: 0.8;
  line-height: 1.4;
}
</style>
