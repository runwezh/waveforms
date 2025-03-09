<script>
  // Import any necessary dependencies
</script>

<footer class="footer">
  <div class="container">
    <p>&copy; {new Date().getFullYear()} Waveforms App</p>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
  </div>
</footer>

<style>
  .footer {
    padding: 1.5rem 0;
    background-color: var(--color-gray-100, #f3f4f6);
    border-top: 1px solid var(--color-gray-200, #e5e7eb);
    margin-top: 2rem;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  ul {
    display: flex;
    list-style: none;
    gap: 1.5rem;
    padding: 0;
    margin: 0;
  }

  a {
    color: var(--color-gray-600, #4b5563);
    text-decoration: none;
  }

  a:hover {
    color: var(--color-gray-900, #111827);
    text-decoration: underline;
  }

  p {
    margin: 0;
  }
</style>