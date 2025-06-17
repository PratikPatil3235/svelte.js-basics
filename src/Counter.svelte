<script>
  let count = 0;

  function handleIncrement(event, stepCounter) {
    count += stepCounter;
  }

  function handleDecrement(event, stepCounter) {
    count -= stepCounter;
  }
</script>

<main>
  <h1>🔥 Count: {count}</h1>

  <div class="btn-group">
    <button on:click={(e) => handleIncrement(e, 1)}>+1</button>
    <button on:click={(e) => handleIncrement(e, 5)}>+5</button>
    <button on:click={(e) => handleIncrement(e, 10)}>+10</button>
  </div>

  <div class="btn-group">
    <button on:click={(e) => handleDecrement(e, 1)}>-1</button>
    <button on:click={(e) => handleDecrement(e, 5)}>-5</button>
    <button on:click={(e) => handleDecrement(e, 10)}>-10</button>
  </div>
</main>

<style>
  :root {
    --primary: #4e8cff;
    --accent: #ff3e00;
    --decrement: #ff6f91;
    --bg: #f4f4f4;
    --text: #222;
  }

  main {
    background: var(--bg);
    text-align: center;
    padding: 2rem;
    max-width: 400px;
    margin: 2rem auto;
    border-radius: 16px;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
    font-family: 'Segoe UI', sans-serif;
  }

  h1 {
    color: var(--accent);
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 600;
    margin-bottom: 1.5rem;
  }

  .btn-group {
    margin-bottom: 1rem;
  }

  button {
    margin: 0.3rem;
    padding: 0.6rem 1.2rem;
    font-size: 1rem;
    font-weight: bold;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
    background-color: var(--primary);
    color: white;
  }

  button:hover {
    background-color: #346fd6;
  }

  .btn-group:last-of-type button {
    background-color: var(--decrement);
  }

  .btn-group:last-of-type button:hover {
    background-color: #e85d7b;
  }
</style>
