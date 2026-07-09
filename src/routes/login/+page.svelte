<script>
  let submitted = false;
</script>

<div class="logo">🔑</div>
<h1>Welcome Back</h1>
<p class="subtitle">Please sign in to access your dashboard.</p>

{#if !submitted}
  <form on:submit|preventDefault={() => submitted = true} class="interactive-box" style="text-align: left; width: 100%; max-width: 400px; box-sizing: border-box; display: inline-block;">
    <div style="margin-bottom: 20px;">
      <label style="display: block; font-size: 0.9rem; font-weight: 600; color: #ff6a00; margin-bottom: 8px;">Username</label>
      <input type="text" placeholder="Enter username" required style="width: 100%; background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 62, 0, 0.2); border-radius: 12px; padding: 12px 16px; box-sizing: border-box; color: #fff; font-size: 0.95rem; outline: none;" />
    </div>
    <div style="margin-bottom: 20px;">
      <label style="display: block; font-size: 0.9rem; font-weight: 600; color: #ff6a00; margin-bottom: 8px;">Password</label>
      <input type="password" placeholder="Enter password" required style="width: 100%; background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 62, 0, 0.2); border-radius: 12px; padding: 12px 16px; box-sizing: border-box; color: #fff; font-size: 0.95rem; outline: none;" />
    </div>
    <button type="submit" class="btn" style="width: 100%;">Sign In</button>
  </form>
{:else}
  <div style="color: #10b981; font-weight: 600; font-size: 1.1rem; margin: 20px 0 30px 0; text-align: center;">
    🎉 Successfully signed in!
  </div>
{/if}

<div class="footer">
  SvelteKit + Shipyard Security Configuration
</div>

<style>
.logo {
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
  font-size: 50px;
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
.interactive-box {
  background: rgba(30, 12, 0, 0.6);
  border-radius: 16px;
  padding: 20px;
  margin-bottom: 30px;
  border: 1px solid rgba(255, 62, 0, 0.1);
}
.btn {
  background: linear-gradient(to right, #ff3e00, #ff6a00);
  color: white;
  border: none;
  padding: 12px 32px;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 14px rgba(255, 62, 0, 0.3);
  transition: transform 0.15s ease;
}
.btn:hover {
  transform: scale(1.02);
  box-shadow: 0 6px 20px rgba(255, 62, 0, 0.5);
}
.footer {
  font-size: 0.85rem;
  color: #ffaa80;
  opacity: 0.8;
}
</style>
