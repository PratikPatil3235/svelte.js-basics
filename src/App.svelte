<script>
  const name = "Batman";
  const gender = "<b>Male</b>";
  const hack = `<a href="#" onclick="alert('You have been hacked!')">Win a Price</a?`;
  const id = "heading";
  const disabled = false;
  const promoted = true;
  const status = "success";
</script>

<main>
  <h2 class="undeline">Underline Text</h2>
  <h2 class={status}>Status</h2>
  <h2 class={promoted ? "promoted" : ""}>Movie Title</h2>
  <h2 class:promoted>RRR</h2>

  <h1>Hello {name}</h1>
  <div>{@html gender}</div>
  <div>{@html hack}</div>
  <h2 {id}>This is a heading</h2>
  <button {disabled}>Bind</button>
</main>

<style>
  .danger {
    color: red;
  }
  .success {
    color: olivedrab;
  }
  .undeline {
    text-decoration: underline;
  }
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .promoted {
    font-style: italic;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
